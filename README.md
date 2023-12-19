
## Link a competencia de Kaggle

- [Binary Classification of VPN Proxy IP Address](https://www.kaggle.com/competitions/vpn-classification/overview)
![Kaggle Competition](https://github.com/pablomoko/Machine-Learning-Kaggle/raw/main/kaggle.png)


## Baseline (Perceptron)
- [Colab](https://colab.research.google.com/drive/1v889q3eAVgOmulz9px-yOWXMRSxwB0ZZ?usp=sharing)

## Datos Baseline
- F1 - Val : 0.5641434262948207
- F1 - Test : 0.53418
- Features:
  - Attack Service | OHE | Se realiza OHE y se agrupa la suma de los servicios de ataques por IP.
  - Attack type | OHE | Se realiza OHE, se suma la cantidad de tipos de ataque y se normalizan para representar las proporciones de ataques por IP.
  - Watcher as name — Mean encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Attacker as name — Mean encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Days — OHE — Se realiza OHE ,se suman las cantidades de las columnas generadas y se normalizan para representar las proporciones de ataques por IP.
  - Attacker country — Binary encodingg — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Watcher country — Binary encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - 
### Feature Importance Plot
- [Colab](https://colab.research.google.com/drive/1v889q3eAVgOmulz9px-yOWXMRSxwB0ZZ?usp=sharing)

## Mejor Modelo (RandomForest)
- [Colab](https://colab.research.google.com/drive/19F8HMtrGq9ygskrYfzuvpLup78dXqdw3?usp=sharing)
## Datos Mejor Modelo
- Elegí hacer este modelo porque Random Forest puede manejar conjuntos de datos desequilibrados, lo que significa que puede trabajar bien cuando las clases objetivo no tienen el mismo número de muestras.
- Este modelo (RandomForest) es el mejor porque el F1 Val dio más alto que el F1 val del modelo 2 (XGB).
- F1 - Val : 0.6044444444444445
- F1 - Test : 0.54545
- Features:
  - Attack Service (nueva feature) | OHE | Se realiza OHE y se agrupa la suma de los servicios de ataques por IP.
  - Attack type (nueva feature) | OHE | Se realiza OHE, se suma la cantidad de tipos de ataque y se normalizan para representar las proporciones de ataques por IP.
  - Watcher as num — Mean encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Attacker as num — Mean encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Days(nueva feature) — OHE — Se realiza OHE ,se suman las cantidades de las columnas generadas y se normalizan para representar las proporciones de ataques por IP.
  - Attacker country — Binary encodingg — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Watcher country — Binary encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - combined countries(nueva feature) — Binary encoding — Se agrupa Attacker con Watcher country y Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - hours(nueva feature) — OHE — Se realiza OHE en rangos de 2hs ,se suman las cantidades de las columnas generadas y se obtiene la cantidad de ataques por rangos de 2hs por IP.
  - ports features — OHE — Se realiza OHE creando nuevas features con los puertos mas comunes VPN y no VPN y el resto, se los coloca en una nueva columna llamada open ports count, que contiene la cantidad de puertos abiertos que no estan en las nuevas features.
  - protocols features — OHE — Se realiza OHE y se obtienen las columnas protocol udp y tcp, y una extra que contiene la cantida de protocolos que utilizo una misma IP.

## Segundo Modelo (XGBClassifier)
- [Colab](https://colab.research.google.com/drive/1bZAtrFiiUVFlrPgyt9efOq-TB8qsYmNB?usp=sharing)
## Datos Segundo Modelo
- Elegí hacer este modelo porque XGBoost está optimizado para un rendimiento rápido y eficiente. Puede entrenar modelos de manera más rápida en comparación con otros algoritmos, especialmente en conjuntos de datos grandes.
- F1 - Val : 0.6026392961876833
- F1 - Test : 0.53584
- Features:
  - Attack Service (nueva feature) | OHE | Se realiza OHE y se agrupa la suma de los servicios de ataques por IP.
  - Attack type (nueva feature) | OHE | Se realiza OHE, se suma la cantidad de tipos de ataque y se normalizan para representar las proporciones de ataques por IP.
  - Watcher as num — Mean encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Attacker as num — Mean encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Days(nueva feature) — OHE — Se realiza OHE ,se suman las cantidades de las columnas generadas y se normalizan para representar las proporciones de ataques por IP.
  - Attacker country — Binary encodingg — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - Watcher country — Binary encoding — Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - combined countries(nueva feature) — Binary encoding — Se agrupa Attacker con Watcher country y Como es unico por IP, no fue necesario hacer ninguna operacion extra
  - hours(nueva feature) — OHE — Se realiza OHE en rangos de 2hs ,se suman las cantidades de las columnas generadas y se obtiene la cantidad de ataques por rangos de 2hs por IP.
  - ports features — OHE — Se realiza OHE creando nuevas features con los puertos mas comunes VPN y no VPN y el resto, se los coloca en una nueva columna llamada open ports count, que contiene la cantidad de puertos abiertos que no estan en las nuevas features.
  - protocols features — OHE — Se realiza OHE y se obtienen las columnas protocol udp y tcp, y una extra que contiene la cantida de protocolos que utilizo una misma IP.
