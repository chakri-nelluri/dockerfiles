# openio/sds Dockerfile

This image provides an easy way to run an OPENIO namespace.  
It deploys and configure a simple non-replicated namespace in a single container.

## How to use this image

OpenIO SDS depends on IPs, meaning that you can't change service IPs after they have been registered to the cluster. By default, Docker networking change you IP when you container restarts which is not compatible with OpenIO SDS at the moment.

### Keep it simple

By default, start a simple namespace listening on 127.0.0.1 inside the container.

```console
docker run -ti --tty openio/sds
```

### Using host network interface

You can start an instance using Docker host mode networking, it allows you to access the services outside your container. You cant specify the interface or the IP you want to use.

Setting the interface:
```console
docker run -ti --tty -e OPENIO_IFDEV=enp0s8 --net=host openio/sds
```

Specifying the IP:
```console
docker run -ti --tty -e OPENIO_IPADDR=192.168.56.101 --net=host openio/sds
```

## Documentation

For a documentation to use the OpenIO Command Line Interface, please refer to this [documentation] (https://github.com/open-io/oiopy/blob/master/docs/cli.md).


