# CALCULO-ACTUARIAL-ll
RESUMEN
# # Cálculo Actuarial II

## Objetivo
Repositorio del curso de Cálculo Actuarial II.

## Entorno
python -m venv .venv
python -m pip install -r requirements.txt

## Estructura
- data/: fuentes y datos procesados
- notebooks/: análisis explicados
- src/: funciones reutilizables
- tests/: validaciones automáticas

## Fuentes
Registrar aquí institucion, producto, anio, URL y fecha de descarga.

---

# Resumen: Cálculo Actuarial II - Unidad I
**Preliminares probabilísticos y entorno computacional reproducible**

## 1. Propósito y Enfoque del Curso
* El cálculo actuarial modela obligaciones inciertas combinando matemáticas, implementación en código (Python) y datos reales.
* El flujo de trabajo busca la **reproducibilidad**, asegurando que cada cálculo pueda entenderse, ejecutarse y verificarse a partir de código, datos e hipótesis.

## 2. Entorno Computacional y Git
* **Herramientas base:** Se utiliza Python, Git, GitHub y Visual Studio Code (VS Code).
* **Estructura del repositorio:** Debe organizarse con carpetas específicas como `data/` (con subcarpetas `raw/` y `processed/`), `notebooks/`, `src/`, `tests/` y `reports/`.
* **Ciclo diario de Git:** Los comandos fundamentales son `git status`, `git add`, `git commit`, `git pull` y `git push`.
* **Buenas prácticas:** Nunca se deben subir contraseñas, tokens ni archivos con datos personales/sensibles; los datos crudos de la carpeta `raw` jamás se editan manualmente.

## 3. Lenguaje de Probabilidad
* **Espacio de probabilidad:** Se define mediante una terna $(\Omega, \mathcal{F}, \mathbb{P})$, donde $\Omega$ es el espacio muestral, $\mathcal{F}$ es la $\sigma$-álgebra de eventos medibles y $\mathbb{P}$ es la medida de probabilidad.
* **Probabilidad condicional e Independencia:** Permite actualizar información (Teorema de Bayes, ley de probabilidad total). Dos eventos son independientes si $\mathbb{P}(A \cap B) = \mathbb{P}(A)\mathbb{P}(B)$.

## 4. Variables Aleatorias y Momentos
* Una variable aleatoria es una función medible $X: \Omega \to \mathbb{R}$.
* Se estudian tanto variables discretas (función de masa de probabilidad) como continuas (función de densidad y de distribución acumulada CDF).
* **Medidas principales:** La esperanza matemática $\mathbb{E}[X]$ (con propiedades de linealidad), la varianza $\text{Var}(X)$, la covarianza y la esperanza condicional.
* **Transformaciones de pérdidas:** Se analizan cuantiles, deducibles ordinarios $Y = (X - d)_+$ y límites $Y = \min(X, u)$.

## 5. Distribuciones Fundamentales
* **Discretas:** 
  * *Bernoulli:* Para ensayos de éxito/fracaso con parámetro $p$.
  * *Binomial:* Suma de variables Bernoulli independientes.
  * *Poisson:* Modelo clásico para conteos de reclamaciones raros y estables (cumple equidispersión $\text{Var}(N) = \mathbb{E}[N]$).
  * *Geométrica:* Número de ensayos hasta el primer éxito.
* **Continuas:** 
  * *Uniforme:* Útil para simulación mediante la transformación inversa.
  * *Exponencial:* Memoria nula e intensidad constante, base para tiempos de espera.
  * *Gamma:* Flexible para severidades con sesgo a la derecha.
  * *Normal:* Importante por el Teorema Central del Límite, aunque con reservas para costos positivos por admitir valores negativos y colas ligeras.

## 6. Riesgo Agregado y Simulación
* **Suma de pérdidas y modelo colectivo:** $S = \sum_{j=1}^{N} X_j$, combinando frecuencia ($N$) y severidad ($X_j$).
* **Ley de los grandes números:** Explica la estabilidad relativa en carteras grandes bajo independencia y momentos finitos. La simulación pseudoaleatoria requiere el uso de semillas para garantizar reproducibilidad.

## 7. Lectura Actuarial de Datos Reales (México)
* Se analizan las **Estadísticas de Defunciones Registradas (EDR)** del INEGI.
* **Conceptos clave a no confundir:** 
  1. *Conteo absoluto* (frecuencia total de eventos).
  2. *Tasa bruta* (referencia agregada por población, ej. por cada 100 mil habitantes).
  3. *Probabilidad individual ($q_x$)* (tasa específica condicionada a la edad y población de riesgo).
