# .NET Core 6 Application in Docker 

Example of .Net Core 6 application running in a docker container

## Command line

Before executing, make sure the sh file has execute permission:

```
cd DockerDotNet
chmod 755 runDocker.sh
chmod 755 buildDocker.sh
```

### Run

To run this container i created a sh file to start docker with the image:

```
./runDocker.sh
```

### Build

To generate the container image, just run sh:

```
./buildDocker.sh
```
