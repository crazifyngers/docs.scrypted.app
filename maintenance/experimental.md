# Experimental

## Cluster Mode

Cluster mode enables distributed computing. Plugin, detection, decode, and encode will automatically be assigned to the best suitable machine in a cluster.

A machine can operate in either `server` or `client` mode. There can only be one `server` machine but there may be multiple `client` machines. The `server` machine will ingest the camera streams, while `client` machines will perform detection. Machines in a cluster can be a mix or operating systems and architectures. For example, you can use a NAS saving video Unraid (`server`) with a Mac Mini performing detection (`client`).

### Cluster Server Setup

The Cluster server will ingest the camera streams and save them to the NVR storage.

Create and edit `~/.scrypted/volume/.env`:

```sh
SCRYPTED_CLUSTER_MODE=server
# this is the IP of this machine.
SCRYPTED_CLUSTER_ADDRESS=192.168.2.130
SCRYPTED_CLUSTER_SECRET=swordfish
```

### Cluster Client Setup

A Cluster client will perform motion and object detection 

Create and edit `~/.scrypted/volume/.env`:

```sh
SCRYPTED_CLUSTER_MODE=client
# this is the IP of this machine.
SCRYPTED_CLUSTER_ADDRESS=192.168.2.131
# this is the IP of the server machine.
SCRYPTED_SERVER_ADDRESS=192.168.2.130
SCRYPTED_CLUSTER_SECRET=swordfish
SCRYPTED_CLUSTER_LABELS=compute
```