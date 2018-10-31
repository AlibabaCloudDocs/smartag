# OSPF状态 {#task_yrz_kwd_qfb .task}

当业务不通时，如果是动态路由接入，可以通过交换机，查看设备和交换机的连通性。

1.  执行如下命令，登录交换机控制台。 

    `telnet 交换机IP`

2.  执行如下命令，查看链路邻居状态。 

    `show ip ospf neighbor`

    系统显示类似如下，查看State值：

    ```
    OSPF process 1, 8 Neighbors, 8 is Full:
    Neighbor ID     Pri   State                BFD State  Dead Time   Address         Interface
    10.10.10.10       0   Full/ -              -          00:00:10    192.168.10.5    GigabitEthernet 0/13
    10.10.10.10       0   Full/ -              -          00:00:10    192.168.10.21   GigabitEthernet 0/46
    ```

3.  执行如下命令，查看OSPF配置信息。 

    ```
    configure terminal
    router ospf
    show this
    ```

    系统显示类似如下，查看area和network的IP：

    ```
    Building configuration...
     !
     router-id 1.1.1.1
     area 1 nssa translator always default-information-originate no-summary
     area 2 nssa translator always default-information-originate no-summary
     area 3 nssa translator always default-information-originate no-summary
     area 17 nssa translator always default-information-originate no-summary
     area 18 nssa translator always default-information-originate no-summary
     area 81 nssa translator always default-information-originate no-summary
     area 90 nssa translator always default-information-originate no-summary
     area 91 nssa translator always default-information-originate no-summary
     network 192.168.10.0 0.0.0.3 area 1
     network 192.168.10.4 0.0.0.3 area 1
     network 192.168.10.20 0.0.0.3 area 1
     network 192.168.20.0 0.0.0.3 area 2
     network 192.168.20.4 0.0.0.3 area 2
     network 192.168.30.0 0.0.0.3 area 0
     network 192.168.67.0 0.0.0.3 area 81
     network 192.168.67.4 0.0.0.3 area 81
     network 192.168.68.4 0.0.0.3 area 81
     network 192.168.68.16 0.0.0.3 area 81
     network 192.168.90.0 0.0.0.3 area 90
     network 192.168.90.4 0.0.0.3 area 90
     network 192.168.91.0 0.0.0.3 area 91
     network 192.168.91.4 0.0.0.3 area 91
     network 192.169.17.0 0.0.0.3 area 17
     network 192.169.17.4 0.0.0.3 area 17
     network 192.169.18.0 0.0.0.3 area 18
     network 192.169.18.4 0.0.0.3 area 18
     !
    end
    ```

4.  执行如下命令，查看连接设备的接口状态。 

    `show ip inter b`

    -   up：表示接口正常。
    -   administratively down：表示接口上配置了shutdown，执行no shutdown命令，使能shutdown。
    -   down：一般表示网线没有接好，检查网线连接。
    系统显示类似如下：

    ```
    Interface                        IP-Address(Pri)      IP-Address(Sec)      Status                 Protocol
    GigabitEthernet 0/2              no address           no address           down                   down
    GigabitEthernet 0/7              192.168.2.7/24       no address           up                     up
    GigabitEthernet 0/11             9.9.9.1/24           no address           down                   down
    GigabitEthernet 0/12             192.168.11.2/24      no address           up                     up
    GigabitEthernet 0/13             192.168.10.6/30      no address           up                     up
    GigabitEthernet 0/15             192.168.40.2/24      no address           down                   down
    GigabitEthernet 0/20             192.168.30.1/30      no address           up                     up
    GigabitEthernet 0/22             192.168.20.2/30      192.169.81.2/30      up                     up
                                                          192.168.12.2/24
    GigabitEthernet 0/23             192.168.20.6/30      192.169.81.6/30      up                     up
    GigabitEthernet 0/27             192.169.80.2/30      no address           up                     up
    GigabitEthernet 0/28             192.169.80.6/30      no address           up                     up
    GigabitEthernet 0/29             192.169.17.2/30      192.168.170.2/30     up                     up
                                                          192.169.170.2/30
    GigabitEthernet 0/30             192.169.17.6/30      no address           up                     up
    GigabitEthernet 0/33             192.168.67.6/30      192.168.68.6/30      down                   down
    GigabitEthernet 0/35             192.169.18.2/30      no address           up                     up
    GigabitEthernet 0/36             192.169.18.6/30      no address           up                     up
    GigabitEthernet 0/37             192.168.90.2/30      192.169.90.2/30      down                   down
                                                          192.168.90.29/30
    GigabitEthernet 0/38             192.168.90.6/30      192.169.90.6/30      down                   down
    GigabitEthernet 0/39             192.168.91.2/30      192.169.91.2/30      administratively down  down
                                                          192.168.91.29/30
    GigabitEthernet 0/40             192.168.91.6/30      192.169.91.6/30      up                     up
    GigabitEthernet 0/43             192.168.254.2/24     no address           up                     up
    GigabitEthernet 0/45             192.168.67.18/30     no address           down                   down
    GigabitEthernet 0/46             192.168.10.22/30     no address           up                     up
    GigabitEthernet 0/48             192.168.10.106/30    no address           down                   down
    Loopback 0                       no address           no address           up                     down
    VLAN 1                           no address           no address           up                     down
    VLAN 4                           192.168.41.1/24      no address           up                     down
    VLAN 19                          192.168.19.2/30      no address           up                     down
    VLAN 47                          192.168.140.2/24     no address           up                     down
    VLAN 148                         172.16.18.1/24       no address           up                     up
    ```

5.  执行如下命令，查看接口下配置的OSPF协商时间和认证等是否匹配。 

    ```
    interface GigabitEthernet 0/39
    show this
    ```

    查看ospf authentica和ospf message-dige对应的认证的参数是否和设备上配置的一致，如果不一致表示设备没有认证，无法建立邻居。

    系统显示类似如下：

    ```
    Building configuration...
     !
     poe enable
     no switchport
     ip ospf network point-to-point
     ip ospf authentication message-digest
     ip ospf message-digest-key 23 md5 888
     ip ospf hello-interval 3
     ip ospf dead-interval 10
     ip ospf priority 0
     no ip proxy-arp
     ip address 192.168.91.2 255.255.255.252
     ip address 192.169.91.2 255.255.255.252 secondary
     ip address 192.168.91.29 255.255.255.252 secondary
     !
    end2 secondary
    ```


