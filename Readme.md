[![Open in](https://img.shields.io/badge/Open%20in-%20Google%20%20Collab%20-orange.svg)](https://colab.research.google.com/github/iLuisOlivares/Sistema-de-control-borroso-de-un-avi-n./blob/main/Parcial_IA.ipynb)

# Sistema de control borroso de un avión. 
Planteamiento del problema: diseñar el Algoritmo de control difuso de vuelo de  un avión
<div>
  <p style = 'text-align:center;' ><img src="https://i.ibb.co/F896Ps2/Captura-de-Pantalla-2022-08-30-a-la-s-0-02-53.png" alt="JuveR" width="300px"></p>
</div>
 
Un avión está sujeto a turbulencias, las que causan que el avión baje o suba bruscamente  formando un ángulo respecto a su línea de vuelo. Se quiere diseñar un sistema de control  difuso para que un piloto automático responda al problema de turbulencia ajustando la  posición del timón de la aeronave. 
Se pide calcular la posición del timón si el avión vuela a 515 km/h y por la turbulencia forma un ángulo de -2.5 grados respecto de su línea de vuelo. Aborde el problema asumiendo los  siguientes valores de entrada para el ACD: 

- Ángulo (grados) = -2.5° 
- Velocidad (km/h) = 515 km/h 

## A partir del conocimiento obtenido empíricamente por los operadores de vuelo, los expertos  en este dominio, se ha definido el siguiente Algoritmo general (Larsen). 
- Intervalo de velocidad [0 a 1000] km/h. 
- Intervalo del Ángulo [-10 a 10] grados 
- Intervalo de Posición [0 a 10] cm 

## Reglas
- R1: SI X1=Alta Y X2=Arriba ENTONCES U1=Medio_baja 
- R2: SI X1 =Alta Y X2=Ok    ENTONCES U1=Medio_baja. 
- R3: SI X1=Alta Y X2=Abajo ENTONCES U1= Baja 
- R4: SI X1=Medio Y X2=Arriba ENTONCES U1=Medio_alta 
- R5: SI X1=Medio Y X2=Ok   ENTONCES U1=Media
- R6: SI X1 =Medio Y X2=Abajo ENTONCES U1=Medio_baja 
- R7: SI X1=Baja Y X2=Arriba ENTONCES U1=Alta 
- R8: SI X1=Baja Y X2=Ok   ENTONCES U1=Medio_alta 
- R9: SI X1=Baja Y X2=Abajo ENTONCES U1=Medio_alta 

## Variables lingüísticas
Variables lingüísticas de entrada: Velocidad del avión y Ángulo con respecto a la línea de vuelo
Variables lingüísticas de salida: Posición del timón

## Terminos lingüísticos
### Variable de entrada X1:Velocidad
- Universo de discurso: [0 a 1000] km/h
- Conjuntos borrosos: X1 ∈ {Alta(700,1000 ), medio(500), Baja(0, 300)} 
### Variable de entrada X2 : Ángulo
- Universo de discurso: [-10 a 10] grados con respecto a la línea de vuelo
- Conjuntos borrosos: X2 ∈ {Arriba(2, 10), Ok(0), Abajo(-10, -2)} 
### Variable de salida U1 : Posición 
- Universo de discurso: [0 a 10] cm
- Conjuntos borrosos: U1 ∈ {Alta(6, 10); Medio_alta(7); Medio(5); Medio_baja(3); Baja(0, 4)}
