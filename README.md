# Análisis de Volatilidad y Modelado GARCH: Caso AMD 📈

Este repositorio contiene un análisis econométrico completo sobre la volatilidad de las acciones de AMD, enfocado en la detección de dependencias no lineales y la gestión de riesgos financieros.

## 🎯 Objetivos del Proyecto
* **Analizar** la serie de tiempo de los precios de cierre de AMD.
* **Validar** los Hechos Estilizados de las series financieras (volatility clustering).
* **Ajustar** un modelo de Heterocedasticidad Condicional Autorregresiva Generalizada (GARCH).
* **Calcular** el Value at Risk (VaR) paramétrico para la gestión de riesgo de mercado.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python 3.x
* **Librerías:** `yfinance`, `pandas`, `numpy`, `statsmodels`, `arch` y `matplotlib`.

## 📊 Metodología Estadística

### 1. Preprocesamiento
Se transformaron los precios de cierre en **log-retornos** para garantizar la estacionariedad, validada mediante el test de Dickey-Fuller.

### 2. Detección de Hechos Estilizados
A través de la inspección de los ACF de los log-retornos al cuadrado y en valor absoluto, se confirmó la existencia de **dependencia no lineal**, justificando el uso de modelos GARCH.

### 3. Modelado GARCH(1,1)
Se ajustó un modelo con la siguiente especificación:
$$\sigma_t^2 = \omega + \alpha \epsilon_{t-1}^2 + \beta \sigma_{t-1}^2$$
El modelo logró que los residuos estandarizados se comporten como ruido blanco.

## 🚀 Resultados Clave
* **Persistencia de Volatilidad:** Se identificó un coeficiente $\beta$ significativo (aprox. 0.63), indicando memoria en el activo.
* **Gestión de Riesgo:** Se implementó un cálculo de **VaR al 95%**, estimando una pérdida máxima de $54,756 para una inversión de $1,000,000.
