## Tema 2: Modelos de programación lineal.
### Introducción: método gráfico.
Los modelos de programación lineal pueden ser resueltos haciendo uso de dos métodos: el gráfico o el simplex, dependiendo del tipo de variables que se puedan tener.
El  procedimiento  gráfico  solamente  lo  utilizaremos  para  la  resolución  de problemas  lineales  con  dos  variables  de  decisión.  Este  procedimiento  tiene  las siguientes fases:  
1. Dibujar  un  sistema  de  coordenadas  cartesianas  en  el  que  las  variables de decisión están representadas por los ejes. 
2. Dibujar las restricciones del problema incluyendo las de no  negatividad. La intersección de todas  las  restricciones determina  lo que se denomina región factible.
3. De todos los puntos de la región factible (puntos que satisfacen  todas las restricciones), se determinan los vértices ya que en uno de ellos será la solución del problema. 
4. Se evalúa la función objetivo en todos los vértices de la región factible y se elige como solución óptima aquel vértice que  maximice o minimice (según sea el caso) el valor de la función objetivo. 

### Ejemplo 1
Wyndor Glass es una empresa que planea lanzar dos nuevos productos: 
1. Una puerta de cristal de 8 pies con marco de aluminio.
2. Una ventana colgante con doble marco de madera de 4 por 6 pies.
La empresa posee 3 plantas:
* Fabrica 1: marcos de aluminio y herrerías.
* Fabrica 2: Elabora marcos de madera.
* Fabrica 3: vidrio y ensambla ventanas y puertas. 

![image](https://user-images.githubusercontent.com/66890535/148234986-1d42da8e-3f91-450a-8929-ba04108137e2.png)

La pregunta a responder consiste en:
¿Qué combinación de productos (número de unidades de producto por semana) maximizan la ganancia?

Para hacerlo en RStudio se usa el código:
```ruby
library(lpSolveAPI)
lp.model = make.lp(0,2)
set.objfn(lp.model, c(300,500))
add.constraint(lp.model, c(1,0), "<=", 4)
add.constraint(lp.model, c(0,2), "<=", 12)
add.constraint(lp.model, c(3,2), "<=", 18)

lp.control(lp.model, sense='max')
print(lp.model)
solve(lp.model)
get.objective(lp.model)
get.variables(lp.model)

#Grafica
plot(0,0, xlim = c(0,10), ylim = c(0,10), xlab = "Unidad P", ylab = "Unidad V", main = "Numero de unidades de P y V")
polygon(c(0,6,0), c(9,0,0), col = "skyblue", density = 30)
abline(h=6, v=4)
```

### Ejemplo 2
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
