# Tema-5
Solución del Laboratorio del tema 5. MPSS


En este laboratorio se requiere calcular la velocidad de atencion de servicio de un servidor que tiene una tasa de arribo de 2 solicitudes por minuto, de tal manera que el servidor este vacio menos del 10% del tiempo. Ademas se debe modificar el codigo proporcionado para realizar la simulacion y comprobacion de dicho problema. 

# Calculo de la velocidad de atencion de solicitudes
Para poder utilizar la formula del primer ejemplo, no podemos utilizarla para calcular cuando el servidor esta vacio (0 clientes en el sistema) pero si podemos utilizarla para calcular cuando no lo está (1 o mas clientes en el sistema) de tal manera que el porcentaje del tiempo que el servidor no esta vacio no puede ser menor al 90% para que cumpla con la condicion solicitada. 

$P(1 \leq  clientes) = \sum_{i=5}^{\propto }(1-\rho )\rho ^{i}=1-\sum_{i=0}^{1}(1-\rho )\rho ^{i}=\rho^{2}$
