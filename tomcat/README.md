对于tomcat镜像的启动命令要使用ENTRYPOINT，当使用CMD时，应该是基础的镜像也有CMD，导致该CMD被重置失效，使用ENTRYPOINT来覆盖之前的CMD。