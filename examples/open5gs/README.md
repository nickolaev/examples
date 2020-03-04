# 4G Network Topology example based on Open5Gs

The goal of this example is to recreate the network topology of a typical 4G network setup using Network Service Mesh.

Web UI - admin/1423

```
                                                     +----------------+         +----------------+
                                                     |                |         |                |
                                                     |     HSS DB     |         |     WEB UI     |
                                                     |                | hss-db  |                |
                                                     |   10.60.5.0/24 <---------+                |
                                                     |                |         |                |
                                                     |    endpoint    |         |     client     |
                                                     +-------^--------+         +----------------+
                                                             |
                                                             |hss-db
                         +----------------+          +-------+--------+         +----------------+
                         |                |          |                |         |                |
                         |       MME      |          |       HSS      |         |      PCRF      |
                 s1-mme  |                |   s6a    |                |         |                |
         +--------------->  10.60.1.0/24  <----------+                |         |                |
         |               |                |          |                |         |                |
         |               |    endpoint    |          |     client     |         |     client     |
         |               +--------^-------+          +----------------+         +--------+-------+
         |                        |                                                      |
         |                        | s11                                   Gx             |
         |                        |                           +--------------------------+
         |                        |                           |
+--------+-------+       +--------+-------+          +--------v-------+         +----------------+
|                |       |                |          |                |         |                |
|   UE + eNB     |       |     SGW        |          |     PGW        |         |     Router     |
|                | s1-u  |                |   s5s8   |                |   SGi   |                |
|                +------->  10.60.2.0/24  +--------->+  10.60.3.0/24  +--------->   10.60.4.0/24 |
|                |       |                |          |                |         |                |
|     client     |       |    endpoint    |          |    endpoint    |         |    endpoint    |
+----------------+       +----------------+          +----------------+         +----------------+
```
https://open5gs.org/
https://github.com/open5gs/open5gs
https://dev.to/infinitydon/virtual-4g-simulation-using-kubernetes-and-gns3-3b7k
https://bitbucket.org/infinitydon/virtual-4g-simulator/src/master/open5gs/