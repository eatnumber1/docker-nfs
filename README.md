# NFS in Docker

This container exports a directory over NFS.

## Usage

```sh
docker run \
	--privileged \
	-p 2049:2049/tcp \
	-p 2049:2049/udp \
	-p 111:111/tcp \
	-p 111:111/udp \
	-p 1066:1066/tcp \
	-p 1067:1067/tcp \
	-p 1067:1067/udp \
	eatnumber1/nfs
```

Now you can `mount -t nfs -o nfsvers=4 hostname:/ <mntpoint>`

## Limitations
 * Only one NFS server can be running on the host at a time.
 * The NFS and Portmap ports (`2049` and `111` respectively) cannot be changed.
