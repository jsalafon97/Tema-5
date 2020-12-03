# Tema-5
Solución del Laboratorio del tema 5. MPSS
#### Jose Sala B66434


En este laboratorio se requiere calcular la velocidad de atencion de servicio de un servidor que tiene una tasa de arribo de 2 solicitudes por minuto, de tal manera que el servidor este vacio menos del 10% del tiempo. Ademas se debe modificar el codigo proporcionado para realizar la simulacion y comprobacion de dicho problema. 

### Calculo de la velocidad de atencion de solicitudes
Para poder utilizar la formula del primer ejemplo, no podemos utilizarla para calcular cuando el servidor esta vacio (0 clientes en el sistema) pero si podemos utilizarla para calcular cuando no lo está (1 o mas clientes en el sistema) de tal manera que el porcentaje del tiempo que el servidor no esta vacio no puede ser menor al 90% para que cumpla con la condicion solicitada. 

<a href="https://www.codecogs.com/eqnedit.php?latex=P(1&space;\leq&space;clientes)&space;=&space;\sum_{i=5}^{\propto&space;}(1-\rho&space;)\rho&space;^{i}=1-\sum_{i=0}^{1}(1-\rho&space;)\rho&space;^{i}=\rho^{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(1&space;\leq&space;clientes)&space;=&space;\sum_{i=5}^{\propto&space;}(1-\rho&space;)\rho&space;^{i}=1-\sum_{i=0}^{1}(1-\rho&space;)\rho&space;^{i}=\rho^{2}" title="P(1 \leq clientes) = \sum_{i=5}^{\propto }(1-\rho )\rho ^{i}=1-\sum_{i=0}^{1}(1-\rho )\rho ^{i}=\rho^{2}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=P(1\geq&space;Clientes)=\rho^{2}=(\frac{\lambda}{\nu})\geq&space;0.90" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(1\geq&space;Clientes)=\rho^{2}=(\frac{\lambda}{\nu})\geq&space;0.90" title="P(1\geq Clientes)=\rho^{2}=(\frac{\lambda}{\nu})\geq 0.90" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\nu^{2}\leq&space;\frac{\lambda}{0.90}=\frac{2^{2}}{0.90}=4.4444\Rightarrow&space;\nu&space;\leq&space;\sqrt{4.444}=2.11" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\nu^{2}\leq&space;\frac{\lambda}{0.90}=\frac{2^{2}}{0.90}=4.4444\Rightarrow&space;\nu&space;\leq&space;\sqrt{4.444}=2.11" title="\nu^{2}\leq \frac{\lambda}{0.90}=\frac{2^{2}}{0.90}=4.4444\Rightarrow \nu \leq \sqrt{4.444}=2.11" /></a>


Entonces el servidor debe atender menos de 2.11 solicitudes por minuto si se desea que pase menos de un 10% vacio. 

### Modificacion del código
Al código base de la simulacion se le debe realizar solo unos pequeños cambios para que sea capaz de comprobar las nuevas espesificaciones.

**Primero:** Hay que cambier el umbral a 0 para que calcula los instantes en que no hay clientes:
```python
  # Umbral de P o más personas en sistema (hay P - 1 en fila)
  P = 0
```
  
**Segundo:** Hay que cambier el ciclo que cuenta los instantes para que sume cada vez que la cantidad de clientes sea igual a P = 0
```python
 # Recorrido del vector temporal y conteo de clientes (estado n)
  for i, c in enumerate(t):
      n += c # sumar (+1) o restar (-1) al estado
      Xt[i] = n
      if Xt[i] == P: 
          frecuencia += 1
 ```
**Tercero:** Se cambio la condicion de frontera y el mensaje de cuando se sumple o no la condicion espesificada (servidor vacio < 10%)
```python
  if fraccion <= 0.1:
     print('\t Sí cumple con la especificación.')
  else:
      print('\t No cumple con la especificación.') 
```

### Resultados:
se corrio 2 veces la simulacion, una vez con un valor de nu=2.1 mayor al calculado teoricamente y una segunda con el valor de nu=2.2 mayor al calculado.

![alt text](https://github.com/jsalafon97/Tema-5/blob/main/nu%3D2.1.PNG)

![alt text](https://github.com/jsalafon97/Tema-5/blob/main/nu%3D2.2.PNG)

Como se puede obserbar en las imagenes anteriores, se cumple la condicion de que el servidor este vacio menos de un 10% del tiempo si el valor de nu (solicitudes atendidas por minuto) es menor a 2.11 y en la simulacion en que es mayor no se cumplen las condiciones.
