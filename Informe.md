## 1. Motivación del trabajo

Bitcoin (BTC) es un activo financiero altamente volátil y descentralizado que ha despertado el interés de inversores, investigadores y analistas. A diferencia de activos tradicionales, su comportamiento está influenciado por factores diversos, incluyendo variables macroeconómicas, sentimiento del mercado, y eventos sociales o tecnológicos. En este trabajo se busca explorar diferentes enfoques de modelado de series de tiempo para anticipar el comportamiento futuro del precio de BTC.

Los objetivos principales del análisis incluyen:

- **Predicción del precio a partir del retorno histórico**:  
  Dado que los precios financieros son generalmente no estacionarios, se transforma la serie a *retornos logarítmicos*, lo que permite trabajar con una serie más estable para el modelado.

- **Predicción del precio a partir de variables exógenas**:  
  Se incorporan variables como el precio del S&P 500, ETH, el índice del dólar (DXY), tasas de interés de la Reserva Federal (FED), y datos de tendencia de búsqueda en Google sobre BTC, con el objetivo de detectar relaciones que puedan mejorar el poder predictivo de los modelos.

- **Detección de cambios de tendencia**:  
  Más allá del valor puntual, se evalúa la posibilidad de anticipar giros importantes en la dirección del precio (de alcista a bajista o viceversa), lo que tiene un valor estratégico para la toma de decisiones.

Estos enfoques se comparan entre sí en términos de precisión de pronóstico, significancia estadística y robustez temporal.

---

## 2. Limitaciones y desafíos

Es importante reconocer que el comportamiento del precio de BTC está influido por una combinación de factores determinísticos y aleatorios. Entre las principales limitaciones del modelado se destacan:

- **Eventos impredecibles**:  
  Cambios abruptos en el precio suelen estar asociados a sucesos difíciles de anticipar, como:
  - Hackeos de exchanges o wallets.
  - Cambios regulatorios en países con fuerte volumen.
  - Anuncios o tweets de figuras públicas influyentes.
  - Crisis financieras o tecnológicas.

- **No linealidad y cambios de régimen**:  
  BTC no sigue un comportamiento estable a lo largo del tiempo; las relaciones entre variables pueden cambiar radicalmente según el contexto (épocas de euforia vs. pánico).

- **Datos limitados o ruidosos**:  
  Algunas fuentes de información, como Google Trends o indicadores sociales, pueden introducir ruido y no reflejar causalidad directa.

Por lo tanto, este trabajo no pretende ofrecer un modelo de predicción perfecto, sino más bien una evaluación crítica y comparativa de diferentes enfoques, entendiendo tanto sus aportes como sus límites dentro del contexto real del mercado cripto.
