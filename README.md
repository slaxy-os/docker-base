# Slax(y)-Base Docker Image

**This docker-image is not purposed as a productive running docker container!** This image just help out with the
creation of custom `*.sb`-modules for your own Slax distribution aka. Slaxy.

## How to use this image

Use this container in combination with the [Slaxy distribution script](https://github.com/slaxy-os/builder) or directly
on the [Slaxy website](https://slaxy.org).

## How to create this module on your own

Create a `root-copy.tar.gz` archive by starting the latest [Slax](http://slax.org) distribution. On the booted system
run the following commands:

```bash
cd /
# maybe mount a device on /mnt or copy the file (e.g over rsync) later...
tar -czf /mnt/root-copy.tar.gz /bin /etc /home /lib /lib64 /opt /root /sbin /srv /usr /var
```

After the creation of the tar-ball you have to copy the file into this folder. Then you are able to create a
docker-image with:

```bash
docker build -t slaxy/base .
```
