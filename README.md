-----------------------------------------------------------

## 📝 INTRODUCCIÓN CHALLENGE TELECOM X PARTE II - ALURA LATAM:

En esta parte 2 del proyecto se busca realizar un modelado predictivo para anticipar la cancelación de clientes en una empresa de telecomunicaciones. Buscando entender los factores que influyen en el abandono y proponer estrategias de retención efectivas.

### 🔍 Variable objetivo:

La variable objtivo se encuentra desbalanceada, esto podría afectar al rendimiento de los modelos, es por esto que es bueno considerar técnicas de balanceo como SMOTE antes de entrenar.
* Aproximadamente el **73.4%** de los clientes NO renuncian **(Churn = 0)**.
* Aproximadamente el **26.6%** sí renuncia **(Churn = 1)**.
---------------------------------------------

## PASOS A SEGUIR:

1. **IMPORTAR BASE DE DATOS TRATADA EN TELECOM X1:**

```bash
    https://raw.githubusercontent.com/frantholy/Telecom_X2_ALURA/main/df_tratado.csv
```
  
2. **DIVIDIR TRAIN/TEST:** Dividir el conjunto de datos en set de entrenamiento y test (80/20).
  
3. **BALANCEAR CON SMOTE:** Balanceamos el set de entrenamiento en (50/50)

4. **MODELAR:** Se escogen 4 modelos para modelado que son Regresión Logística, SVM, Árbol de Decisión, KNN.
  
5. **EVALUAR MÉTRICAS DE DESEMPEÑO:** Se evaluan las métricas de desempeño de los modelos, se evaluan curvas ROC y se escoge mejor modelo.
   
6. **EVALUAR PROBABILIDAD DE CHURN, CARACTERÍSTICAS MÁS IMPORTANTES:** Con el mejor modelo escogido se identifican los 10 clientes con mayor probabilidad de CHURN, las 10 características más importantes para el modelo y se define cuáles aportan mayor o menor incidencia en CHURN.

7. **CONCLUSIONES Y RECOMENDACIONES** Conclusiones de CHURN y recomendaciones para mantener a los clientes.

***Te invito a revisar el documento telecomX2_ALURA.ipynb adjunto en el proyecto para visualizar los gráficos y sus respectivos análisis en detalle***

----------------------------------------

## 📊 Análisis de las métricas de desempeño de los modelos:

- **Regresión Logística** es el modelo más equilibrado y con mejor rendimiento global en todas las métricas.
- **SVM** es un segundo lugar sólido, especialmente en **AUC-ROC** y **Accuracy**.
- **Árbol de Decisión** destaca en Recall, pero con menor precisión, lo que implica más falsos positivos.
- **KNN** tiene el peor desempeño general, lo que sugiere dificultades para capturar la estructura de los datos, posiblemente por **alta dimensionalidad o ruido**.

----------------------------------------
## MEJOR MODELO REGRESIÓN LOGÍSTICA

## 🔹 Insights por característica:

- **tenure (1.32, Menor):** Clientes con más tiempo de permanencia tienen menos probabilidad de churn. Es la característica más importante y protege contra la renuncia.

- **Contract_Two year (1.28, Mayor):** Tener un contrato de dos años aumenta la probabilidad de churn según el modelo.

- **InternetService_No (0.85, Menor):** Clientes sin servicio de Internet tienen menor probabilidad de churn.

- **InternetService_Fiber optic (0.80, Menor):** La red por fibra óptica es más estable, se asocia con menor churn. 

- **Contract_One year (0.70, Menor):** Contratos de un año disminuyen el churn, al contrario del contrato de dos años.

- **TotalCharges (0.61, Menor):** Clientes con mayor gasto total tienden a quedarse más tiempo.

- **TechSupport (0.43, Mayor):** Tener soporte técnico se asocia con mayor churn. Podría indicar que quienes usan soporte tienen problemas recurrentes y podrían irse.

- **PhoneService (0.41, Menor):** Tener servicio de teléfono disminuye la probabilidad de churn.

- **PaperlessBilling (0.37, Menor):** Facturación electrónica se asocia con menor churn, aunque su importancia es baja.

- **PaymentMethod_Electronic check (0.36, Menor):** Usar cheque electrónico disminuye ligeramente el churn, siendo la menos influyente de estas 10
características.

---------------------------------------

## 🔹 Recomendaciones para reducir churn

- **Fidelizar clientes antiguos:** Ofrecer beneficios y reforzar comunicación para quienes llevan más tiempo con el servicio.  
- **Revisar contratos largos:** Analizar los contratos de dos años y ofrecer flexibilidad o incentivos para mantenerlos.  
- **Mejorar soporte técnico:** Optimizar tiempos de respuesta, seguimiento proactivo y recursos de autoservicio.  
- **Fortalecer experiencia de Internet:** Garantizar estabilidad, velocidad y paquetes atractivos según el tipo de servicio.  
- **Incentivar servicios complementarios:** Combinar teléfono, Internet y soporte para aumentar la retención.  
- **Facilitar facturación y pagos:** Promover facturación electrónica y recordatorios de pago.  
- **Monitorear gastos de clientes:** Identificar clientes de bajo gasto y ofrecer promociones, premiar clientes de alto gasto.

--------------------------

## TECNOLOGÍAS UTILIZADAS

- **Python**: Lenguaje para el análisis de datos.
  
------

## CARGAR EL PROYECTO O CLONAR:

   Abre tu terminal o línea de comandos y ejecuta el siguiente comando para clonar el proyecto:

   ```bash
   git clone https://github.com/frantholy/Telecom_X1_ALURA
```

------------------
