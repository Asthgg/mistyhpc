# mistyhpc
High performance computing project

## Colfax
Los laboratorios del MOOC se encuentran en la carpeta [Colfax labs](./ColfaxLabs)

#### Hello World

Compilar un Hola mundo en el clúster. Se debe modificar el archivo Makefile para que use el compilador C++ de Intel, luego hacer un zip de éste únicamente y subirlo a la página de Colfax.

Pasos para ejecutar en el clúster
```
> Añadir línea faltante: icpc -o "$@" "$<"
```
![alt text](https://github.com/Asthgg/mistyhpc/static/images/missingLine.png "Image Makefile")
```
> zip -r helloworld.zip .
> scp hellowordl.zip colfax:/home/u48834
> ssh colfax
> unzip helloworld.zip
> make -f Makefile
> ./app-gcc
```
![alt text](https://github.com/Asthgg/mistyhpc/static/images/app-gcc.png "Image app-gcc output")
```
> ./app-icc
```
![alt text](https://github.com/Asthgg/mistyhpc/static/images/app-icc.png "Image app-icc output")



