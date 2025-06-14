## 1. Recolección y armado del dataset
- [x] Identificar fuentes confiables  
  - **BTC price & volume** (e.g. CoinAPI, Binance, Glassnode)  
  - **ETH price**, **S&P 500**, **DXY** (Índice del dólar)  
  - **Tasas de interés FED** (FRED)  
  - **Google Trends “bitcoin”**  
- [ ] Sincronizar todas las series a la misma frecuencia (diaria) y zona horaria  
- [x] Guardar CSV/Parquet crudos en `../data/raw/`

## 2. Limpieza y preparación
- [ ] Chequear y rellenar/marcar valores faltantes  
- [ ] Remuestrear si hay huecos (forward‑fill/linear)  
- [ ] Crear variables **log‑return** y **volatilidad intradía**  
  - Definir horizonte: diaria vs. semanal  
- [ ] Generar variables exógenas rezagadas (lag 1, 7, 30)

## 3. Análisis exploratorio
- [ ] `seasonal_decompose` / STL para cada serie  
- [ ] Visualizar correlaciones y *heatmaps*  
- [ ] Pruebas ADF/KPSS para estacionariedad  
- [ ] Determinar necesidad de diferenciación o transformación

## 4. Definición de objetivos
- [ ] Predicción de precio a partir de predicción de retorno
- [ ] Predicción de precio a partir de otras variables
- [ ] ¿Predicción de cambio de tendencia?
- [ ] ¿Otro?

## 4. Construcción de modelos
- **Modelos univariados**  
  - [ ] ARIMA / SARIMA (criterio Box‑Jenkins)
    - Probar AUTOARIMA (solo mira el AKAIKE)
  - [ ] GARCH (modelar volatilidad)  
- **Modelos multivariados** (para utilizar varias features al mismo tiempo)  
  - [ ] VAR / VARMAX
  - [ ] XGBoost con *lags* y features exógenas
  - [ ] Transformers
    - Informers
    - Revisar si cantidad de datos es suficiente para un Transformer
    - Quizás solo hace sentido para predecir con datos a minuto/segundo, no diario.
- **Modelos deep‑learning**  
  - [ ] LSTM / GRU con *sliding window*  
- **Procesos estocásticos**  
  - [ ] GBM (browniano geométrico) para *benchmark*
- **Prophet**
  - [ ] Renombrar columnas a 'ds', 'y'. Colocar datos de tiempo en su propia columna
  - [ ] Ver bandas obtenidas
  - [ ] Ver como comparar modelo con los otros
  - [ ] Ver si predice cambios de tendencia
- [ ] Documentar hiperparámetros probados

## 5. Entrenamiento y validación
- [ ] Definir *train/validation/test* con corte temporal (p.ej. 70/15/15%)  
- [ ] Backtesting con ventana deslizante  
- [ ] Registrar métricas:  
  - **RMSE**, **MAE**, **MAPE**  
  - **AIC / BIC** (modelos paramétricos)  
  - **p‑values <0.05** para significancia de parámetros

## 6. Diagnóstico y comparación
- [ ] Revisar residuos (Ljung‑Box, Jarque‑Bera)
  - revisar si esto tiene sentido
- [ ] Graficar pronósticos vs. realidad  
- [ ] Tabla comparativa de métricas y ranking de modelos  
- [ ] Seleccionar “campeón” + “runner‑up”

## 7. Pronósticos finales
- [ ] Generar *forecast* 30‑90 días para:  
  - Precio BTC  
  - Volatilidad (σ)  
- [ ] Escenarios con variables exógenas (stress–test FED rate ↑)

## 8. Informe Markdown/LaTeX
- [ ] Redactar pregunta de investigación  
- [ ] Describir dataset y fuentes  
- [ ] Explicar modelos y supuestos  
- [ ] Presentar resultados, gráficos y conclusiones  
- [ ] Lecciones aprendidas y trabajo futuro
