## Tema 2: Modelos de programación lineal.
### Introducción: método gráfico.
Los modelos de programación lineal pueden ser resueltos haciendo uso de dos métodos: el gráfico o el simplex, dependiendo del tipo de variables que se puedan tener.
El  procedimiento  gráfico  solamente  lo  utilizaremos  para  la  resolución  de problemas  lineales  con  dos  variables  de  decisión.  Este  procedimiento  tiene  las siguientes fases:  
1. Dibujar  un  sistema  de  coordenadas  cartesianas  en  el  que  las  variables de decisión están representadas por los ejes. 
2. Dibujar las restricciones del problema incluyendo las de no  negatividad. La intersección de todas  las  restricciones determina  lo que se denomina región factible.
3. De todos los puntos de la región factible (puntos que satisfacen  todas las restricciones), se determinan los vértices ya que en uno de ellos será la solución del problema. 
4. Se evalúa la función objetivo en todos los vértices de la región factible y se elige como solución óptima aquel vértice que  maximice o minimice (según sea el caso) el valor de la función objetivo. 


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
