## Tema 2: Modelos de programación lineal.

### Ejemplo en clase
Un sastre elabora dos tipos de trajes para hombre, blazer y ejecutivos y a su vez, se cuenta con dos procesos: corte y costura: 

Hacer un traje tipo blazer requiere 1 hora de corte y 1 hora de costura, mientras que uno de tipo ejecutivo requiere 1 hora de corte y 2 de costura. El sastre trabaja un total de 4 horas al día en corte y en el proceso de costura 6 horas. Las ganancias por la venta de un traje tipo blazer es $2 por unidad y $3 por cada traje tipo ejecutivo vendido. Lo que se pide es entonces maximizar ganancias.

1. Calcula cuantos tipos de cada traje hacer para maximizar las ganancias. 

Para hacerlo en RStudio se usa el código:
```ruby
library(boot)
A1<-rbind(c(1,1),c(1,2))
b1<-c(4,6)
a<-c(2,3)
simplex(a=a,A1=A1,b1=b1,maxi="TRUE")
```
