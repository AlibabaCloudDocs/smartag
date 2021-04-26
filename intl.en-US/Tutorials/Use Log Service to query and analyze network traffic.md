# Use Log Service to query and analyze network traffic

This topic describes how to use Log Service to query and analyze the network traffic of a Smart Access Gateway \(SAG\) instance.

-   A project and a Logstore are created in Log Service. For more information, see [Quick start](/intl.en-US/.md).
-   The SAG device is connected to Alibaba Cloud. For more information, see [Deploy an SAG device in one-arm mode and enable dynamic routing](/intl.en-US/Tutorials/Deploy an SAG device in one-arm mode and enable dynamic routing.md).
-   The model of the SAG device is SAG-1000.

SAG supports flow logs. You can use flow logs to capture network traffic that is distributed by SAG instances. Flow logs can be stored in Log Service or on a specified NetFlow collector. In this topic, Log Service is used as an example. This topic describes how to store the traffic information about an SAG instance, and query and analyze the collected information. This allows you to gain insights into the network traffic distribution of SAG instances.

## Step 1: Add a data source

Before you can query or analyze network traffic, you must perform the following steps to collect and deliver the traffic information about the SAG instance to the specified Logstore in the Log Service project:

1.  Create a flow log.

    In the SAG console, create a flow log for the SAG instance. Each flow log is associated with a Logstore in a Log Service project. Traffic information about the SAG instance is stored in the associated project and Logstore.

    1.  Log on to the [SAG console](https://smartag.console.aliyun.com).

    2.  In the left-side navigation pane, click Flow Log.

    3.  On the Flow Log page, click **Create Flow Log**.

    4.  In the **Create Flow Log** panel, set the parameters and click **OK**.

        -   **Name**: Enter a name for the flow log.
        -   **Output Interval Under Active Connections**: Enter a time interval at which log data of active network connections is collected. The default time interval is 300 seconds. You can set a time interval from 60 to 6,000 seconds.
        -   **Output Interval Under Inactive Connections**: Enter a time interval at which log data of inactive network connections is collected. The default time interval is 15 seconds. You can set a time interval from 10 to 600 seconds.
        -   **Deliver Flow Log Data To**: Select a service where you want to store the collected log data. **SLS** is selected in this example.
            -   If you want to store the collected log data in Log Service, select **SLS**.
            -   If you want to store the collected log data on a NetFlow collector, select **Netflow**.
            -   To store log data both in Log Service and on a NetFlow collector, select **ALL**.
        -   **SLS Region**: Select the region where Log Service is deployed.
        -   **SLS Project**: Select the project to which the Logstore belongs.
        -   **SLS Logstore**: Select the Logstore where you want to store the collected log data.
        For more information, see [Create a flow flog](/intl.en-US/Configuration Guide/Flow logs/Create a flow flog.md).

2.  Associate the flow log with the SAG instance.

    After you create a flow log, you must associate it with the SAG instance from which you want to collect traffic information. After the flow log is associated with the SAG instance, the information about the network traffic of the SAG instance is stored in the specified Log Service project and Logstore. You can query and analyze the collected log data in the Log Service console.

    1.  On the Flow Log page, find the flow log that you have created and click its ID.

    2.  On the details page, click **Associate with Instance**.

    3.  In the **Associate with Instance** panel, select the SAG instance with which you want to associate the flow log and click **Save**.


## Step 2: Query and analyze log data

After the flow log is associated with the SAG instance, you can query and analyze the collected log data in the Log Service console.

1.  Log on to the [Log Service console](https://sls.console.aliyun.com).

2.  In the Projects section, click the project in which you want to query and analyze logs.

3.  On the **Log Storage** \> **Logstores** tab, click the Logstore where logs are stored.

4.  Enable the indexing feature for the Logstore. For more information, see [Enable and configure the indexing feature for a Logstore](/intl.en-US/Index and query/Configure indexes.md).

    An index is a data structure that can be used to sort one or more columns of log data. You can query and analyze log data only after you add indexes. The query and analysis results vary based on the indexes. We recommend that you add indexes based on your business requirements. In this example, the field indexing and statistics features are enabled:

    ![Field indexing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5468134161/p232776.png)

    **Note:** To facilitates data analytics, make sure that the bytes field is of the TEXT type when you configure field indexing.

5.  After you enable indexing, you can query and analyze log data. In the following example, the top ten 5-tuples that have generated the highest volume of network traffic are queried. The example shows how to query and analyze network traffic.

    1.  Enter a query statement in the search box.

        In this example, the following fields are used to query the top ten 5-tuples that have generated the highest volume of network traffic: srcaddr, srcport, dstaddr, dstport, and protocol.

        ```
        
        * | select srcaddr,srcport,dstaddr,dstport,protocol,count(*) as num,sum(bytes) as bytes
        from (select CASE
        WHEN strpos(bytes, 'M') ! = 0 then
        (CAST(replace(bytes,'M') AS double)*1024*1024)
        WHEN strpos(bytes, 'K') ! = 0 then
        (CAST(replace(bytes,'K') AS double)*1024)
        else CAST(bytes AS double) end
        as bytes,srcaddr,srcport,dstaddr,dstport,protocol from log limit 100000)
        GROUP BY srcaddr,dstaddr,srcport,dstport,protocol ORDER BY bytes DESC limit 10
                                        
        ```

        By default, the system returns log data collected within the last 15 minutes. You can also specify a time range.

        ![Query and analyze data](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5468134161/p236449.png)

        **Note:** Do not directly include the fields described in this topic in the query statements. These fields are for reference only. The fields in the collected log shall prevail. For more information, see [Log search](/intl.en-US/Index and query/Log search.md).

    2.  Click **Search & Analyze**.

        You are redirected to the **Graph** tab. The information about the top ten 5-tuples that have generated the highest volume of network traffic is displayed in a table. You can also choose to display the data in other types of graph. For more information, see [Overview](/intl.en-US/Query and visualization/Analysis graph/Overview.md).

        In this example, the data is displayed in a pie chart.

    3.  On the **Graph** tab, you can modify the attributes of the pie chart.

        The following attributes are modified in this example. Other attributes use the default value. For more information, see [Display query results on a pie chart](/intl.en-US/Query and visualization/Analysis graph/Display query results on a pie chart.md).

        -   **Category**: The category of the data.

            In this example, the data is classified based on the following fields: srcaddr, srcport, dstaddr, dstport, and protocol. The volume of network traffic is counted only if all the preceding fields match the specified conditions.

        -   **Value Column**: The value of the returned data entry.

            In this example, the bytes field is used as the value column.

        ![The pie chart base on 5-tuples](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5468134161/p232554.png)

6.  You can perform the preceding steps to query the top ten 3-tuples that have generated the highest volume of network traffic or the top 10 source IP addresses that have generated the largest amount of network traffic.

    -   Query the top ten 3-tuples that have generated the highest volume of network traffic
        -   Fields that are queried: srcaddr, dstaddr, protocol.
        -   Statements for querying data:

            ```
            
            * | select srcaddr,dstaddr,protocol,count(*) as num,sum(bytes) as bytes
            from (select CASE
            WHEN strpos(bytes, 'M') ! = 0 then
            (CAST(replace(bytes,'M') AS double)*1024*1024)
            WHEN strpos(bytes, 'K') ! = 0 then
            (CAST(replace(bytes,'K') AS double)*1024)
            else CAST(bytes AS double) end
            as bytes, srcaddr,dstaddr,protocol from log limit 100000)
            GROUP BY srcaddr,dstaddr,protocol ORDER BY bytes DESC limit 10
                                                    
            ```

        -   Query results:

            ![The pie chart based on 3-tuples](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5468134161/p232850.png)

    -   Query the top 10 source IP addresses that have generated the highest volume of network traffic
        -   Fields that are queried: srcaddr and dstaddr.
        -   Statements for querying data:

            ```
            * | select srcaddr,dstaddr,count(*) as num,sum(bytes) as bytes
            from (select CASE
            WHEN strpos(bytes, 'M') ! = 0 then
            (CAST(replace(bytes,'M') AS double)*1024*1024)
            WHEN strpos(bytes, 'K') ! = 0 then
            (CAST(replace(bytes,'K') AS double)*1024)
            else CAST(bytes AS double) end
            as bytes, srcaddr,dstaddr from log limit 100000)
            GROUP BY srcaddr,dstaddr ORDER BY bytes DESC limit 10
            ```

        -   Query results:

            ![The pie chart based on source IP addresses](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5468134161/p232851.png)


## Step 3: \(Optional\) Add the graph to a dashboard

Log Service allows you to add graphs that contain query results to dashboards. This way, you can view the stored data as needed.

1.  In the upper-right corner of the pie chart, click **Add to New Dashboard**.

2.  In the **Add to New Dashboard** dialog box, set the parameters and click **OK**.

    -   **Operation**: **Create Dashboard** is selected in this example.
    -   **Dashboard Name**: Enter a name for the dashboard. Statistics Based on 5-tuples is used in this example.
    -   **Chart Name**: Enter a name for the graph. Pie Chart Based on 5-tuples is used in this example.
    For more information, see [Add an analysis chart to a dashboard](/intl.en-US/Query and visualization/Dashboard/Add an analysis chart to a dashboard.md).

3.  In the left-side navigation pane, click the **Dashboard** icon.

4.  Click the name of the dashboard that you have created to view the data.

    On the dashboard, you can click **Time Range** to specify a time range to filter analysis data. For more information, see [Configure a dashboard in the display mode](/intl.en-US/Query and visualization/Dashboard/Configure a dashboard in the display mode.md).

    ![The dashboard](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3901249161/p232825.png)


