# Tema-5
Solución del Laboratorio del tema 5. MPSS


En este laboratorio se requiere calcular la velocidad de atencion de servicio de un servidor que tiene una tasa de arribo de 2 solicitudes por minuto, de tal manera que el servidor este vacio menos del 10% del tiempo. Ademas se debe modificar el codigo proporcionado para realizar la simulacion y comprobacion de dicho problema. 

# Calculo de la velocidad de atencion de solicitudes
Para poder utilizar la formula del primer ejemplo, no podemos utilizarla para calcular cuando el servidor esta vacio (0 clientes en el sistema) pero si podemos utilizarla para calcular cuando no lo está (1 o mas clientes en el sistema) de tal manera que el porcentaje del tiempo que el servidor no esta vacio no puede ser menor al 90% para que cumpla con la condicion solicitada. 

<a href="https://www.codecogs.com/eqnedit.php?latex=P(1&space;\leq&space;clientes)&space;=&space;\sum_{i=5}^{\propto&space;}(1-\rho&space;)\rho&space;^{i}=1-\sum_{i=0}^{1}(1-\rho&space;)\rho&space;^{i}=\rho^{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(1&space;\leq&space;clientes)&space;=&space;\sum_{i=5}^{\propto&space;}(1-\rho&space;)\rho&space;^{i}=1-\sum_{i=0}^{1}(1-\rho&space;)\rho&space;^{i}=\rho^{2}" title="P(1 \leq clientes) = \sum_{i=5}^{\propto }(1-\rho )\rho ^{i}=1-\sum_{i=0}^{1}(1-\rho )\rho ^{i}=\rho^{2}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=P(1\geq&space;Clientes)=\rho^{2}=(\frac{\lambda}{\nu})\geq&space;0.90" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(1\geq&space;Clientes)=\rho^{2}=(\frac{\lambda}{\nu})\geq&space;0.90" title="P(1\geq Clientes)=\rho^{2}=(\frac{\lambda}{\nu})\geq 0.90" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\nu^{2}\leq&space;\frac{\lambda}{0.90}=\frac{2^{2}}{0.90}=4.4444\Rightarrow&space;\nu&space;\leq&space;\sqrt{4.444}=2.11" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\nu^{2}\leq&space;\frac{\lambda}{0.90}=\frac{2^{2}}{0.90}=4.4444\Rightarrow&space;\nu&space;\leq&space;\sqrt{4.444}=2.11" title="\nu^{2}\leq \frac{\lambda}{0.90}=\frac{2^{2}}{0.90}=4.4444\Rightarrow \nu \leq \sqrt{4.444}=2.11" /></a>
