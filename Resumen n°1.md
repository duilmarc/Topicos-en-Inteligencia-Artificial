<p align="center">
 <h1>Resumen de Redes Neuronales </h1>
</p>

## 1.-Resnet

### Arquitectura

### Características

- Introduco el concepto de aprendizaje residual
- 20 y 8 veces mas profunda que AlexNet y VCG respectivamente y posee menos complejidad computacional que estas dos

### Ventajas

- Menos complejidad computacional que la VGG y AlexNet
- Buen desempeño en tarea de reconocimiento y localización de imágenes

### Desventajas

## 2.- Highway

### Arquitectura

<p align="center">
<img src="highway.png">
</p>

#### Como funciona:

Tenemos : 
<br>
` x : entrada , w : pesos, H: función activación , y : salida`
- Las Highway poseen dos transformaciones no-lineales: T y C , donde T es la "transforation gate" y la C es la " carry gate"
<br>` y = H(x, W(h)). T(x,w(t)) + x.C(x,W(c))`
- En particular : `C = 1 - T` 
- ` y = H(x , W(h) ). T(x, w(t)) + x.(1 - T(x,W(t))) `
- Se tiene las siguientes condiciones para T : 
```
    y = x , si T(x,W(t)) = 0 
    y = H(x, w(h)) , si T(x,W(t)) = 0

```




### Características

- Se categoriza como una Red Neuronal MultiPath
- Inspirada por la LSTM
- Posee un mecanismo de cross-layer connectivity.

- Hace uso de la función de activación para transformar adaptativamente o evitar la señal para que la red pueda profundizarse
-Se agrega información de la L capa y la información de las capas previas l - j creando un efecto de regularización, haciendo de la gradiente basada en entrenamiento de la red profunda sin cambio.

### Ventajas

- Convergen significativamente más rápido que las planas
- Enriquecen representación de caracteristicas e introduce a un nuevo mecanismo de conectividad entre capas
- Permite el entraniemto de mas de 100 capas , incluso con 900 capas usando el algoritmo de la gradiente descendente estocástica

### Desventajas

- Lento entrenamiento y velocidad de convergencia
- El rendimiento decrece cuando se añaden unidades ocultas bajo las 10 capas

## 3.- DenseNet

### Arquitectura

### Ventajas

### Características

### Desventajas

## 4.- Xception

### Arquitectura

### Ventajas

### Desventajas

## Terminos

- Cross-layer connectivity : Comunicación entre capas permitiendo que una capa acceda a la data de otra para intercambio de la información y una disponible interacción ( cross-layer network )
- Multipaths: Pueden sistematicamente conectar una capa con otra evitando alguna capa intermediaria capa para permitir el flujo especializado de información entre capas. Busca resolver el problema del desvanecimiento de la gradiente por hacer que esta misma sea accesible a capas inferiores.
