# Actividad-6-filtro-de-Kalman
## Robotortugas

### a) ¿Cuál es el comportamiento del movimiento de translación del Sistema? ¿Cuál es el comportamiento del movimiento de rotación del Sistema?

Cambios en la posición en X, Y y theta, en las tres iteraciones 
![Screenshot from 2024-05-24 13-27-00](https://github.com/DanaRiva/Actividad-6-filtro-de-Kalman/assets/100874942/b6dc4cb8-769b-411a-a3de-7024bf0256b4)

En el caso del movimiento lineal, tenemos un movimiento progresivo en el cambio de posición en X, hay una gran diferencia en la posición entre las últimas dos iteraciones, a pesar de que la velocidad se mantiene constante en todas las 
iteraciones del modelo, pero hay un ajuste diferente entre las iteraciones, en el caso del desplazamiento en Y hay un cambio menor en la posición quealcanza, esto también se debe a las lecturas reales no se genera un gran cambio en las posciiones de y, por lo que no se refleja una gran diferencia en los cambios de posición.

Para la rotación del sistema, se debe generar una rotación aproximada de 45° para llegar a la posición deseada, se genera una rotación en el robot que llega aproximadamente a 33° en la última iteración, se hacen las correcciones de la pose
de manera progresiva y lenta por la baja velocidad que se mantiene constante en las tres iteraciones del sistema.

### b) ¿Cómo es la evolución de las matrices de covarianza?
Matriz primera iteración

![Screenshot from 2024-05-24 13-59-14](https://github.com/DanaRiva/Actividad-6-filtro-de-Kalman/assets/100874942/97180e15-7832-4eb3-a804-f0ebcc29e6a4)

Matriz segunda iteración

![Screenshot from 2024-05-24 13-58-44](https://github.com/DanaRiva/Actividad-6-filtro-de-Kalman/assets/100874942/8e1956e5-4740-4153-9d7e-cee97d194b57)

Matriz tercera iteración

![Screenshot from 2024-05-24 13-57-03](https://github.com/DanaRiva/Actividad-6-filtro-de-Kalman/assets/100874942/24105326-694c-48d1-bfa2-681b23cb003d)

Se van reduciendo los valores de las matrices de covarianza, lo que nos puede representar una respectiva reducción en las incertidumbres, generando mejores estimaciones de la posición real del robot con respecto a las lecturas de los sensores y las estimaciones ideales generadas por el modelo de posición 

### d) Modifica los parámetros de las velocidades y responde lo siguiente: ¿tiene el mismo comportamiento el Sistema?, ¿qué ocurre si aumentan las velocidades?, ¿que ocurre si disminuyen las velocidades?

Al momento de aumentar la velocidad lineal y angular el sistema se sigue comportando de manera similar a cuando tiene una velocidad constante de 1, la principal diferencia que se puede apreciar es el aumento en el desplazamiento lineal y angular a comparación de las iteraciones con los valores orifinales, de manera contraria al disminuir las velocidades se reduce el desplazamiento, sin embargo a pesar de haber reducido la velocidad a la mitad del valor original no se presenta un cambio muy drástico con respecto al desplazamiento original, tanto en las posiciones finales como en los intérvalos en los que se genera el cambio. Tampoco se presenta un cambio muy significativo en las matrices de covarianza.

### e) Modifica los parámetros de las matrices de covarianzas y responde lo siguiente: ¿tiene el mismo comportamiento el Sistema?, ¿qué ocurre si aumentan los parámetros de la matriz Qk?, ¿qué ocurre si aumentan los parámetros de la matriz Rk? 

Si cambiamos los valores iniciales de la matriz de covarianza al comparar las salidas de cada iteración con las salidas de sigma y del vector de posición podemos ver que no se genera una gran diferencia entre las salidas, o al menos no es una diferencia verdaderamente importante, los valores de salida no varían mucho mostrando un comportamiento similar en ambos casos.

Al cambiar los valores de Qk, se genera un cambio en la covarianza proporcional a la variación generada en la matriz, sin embargo a pesar de casi duplicar o triplicar los valores no se percibe un cambio muy significativo en los valores de la covarianza en las iteraciones.

Con los cambios en la matriz Rk podemos ver cabios en las posiciones lineales y angulares, así como un incremento en los valores de las matrices de covarianza de salida de cada iteración.
