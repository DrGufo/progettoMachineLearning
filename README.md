# Progetto Machine Learning - Classificazione da Dataset Sklearn

## Descrizione
Questo progetto presenta una pipeline completa di machine learning supervisionato per la classificazione della qualita delle mele (`good` / `bad`) a partire da caratteristiche fisico-chimiche.

L'analisi e l'addestramento sono sviluppati nel notebook `EsercizioDatasetSklearn.ipynb`, con confronto tra piu algoritmi di classificazione, ottimizzazione degli iperparametri, valutazione tramite metriche standard e salvataggio del modello finale.

## Obiettivi
- Analizzare e preparare il dataset `apple_quality.csv`.
- Addestrare e confrontare diversi modelli di classificazione.
- Valutare le prestazioni con metriche robuste (Accuracy, Precision, Recall, F1, ROC-AUC).
- Selezionare e serializzare il modello migliore per riutilizzo in fase di inferenza.

## Struttura Del Progetto
```text
progettoMachineLearning/
|-- apple_quality.csv
|-- EsercizioDatasetSklearn.ipynb
|-- README.md
```

## Stack Tecnologico
- Python 3.10+
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Seaborn
- scikit-learn
- Colorama
- Pickle (modulo standard Python)

## Requisiti
- Python 3.10 o superiore installato sul sistema.
- `pip` aggiornato.
- Ambiente virtuale consigliato per isolamento delle dipendenze.

## Installazione E Setup
1. Clonare il repository:
```bash
git clone https://github.com/DrGufo/progettoMachineLearning.git
cd progettoMachineLearning
```

2. Creare un ambiente virtuale:
```bash
python -m venv .venv
```

3. Attivare l'ambiente virtuale:

Windows (PowerShell):
```powershell
.\.venv\Scripts\Activate.ps1
```

Linux/macOS:
```bash
source .venv/bin/activate
```

4. Installare le dipendenze:
```bash
pip install --upgrade pip
pip install numpy pandas matplotlib seaborn scikit-learn colorama jupyter
```

## Esecuzione Del Progetto
### Modalita interattiva (consigliata)
1. Avviare Jupyter:
```bash
jupyter notebook
```
2. Aprire `EsercizioDatasetSklearn.ipynb`.
3. Eseguire tutte le celle in ordine (`Run All`) per riprodurre l'intera pipeline.

### Modalita batch (esecuzione automatica)
Per eseguire il notebook in modo non interattivo:
```bash
jupyter nbconvert --to notebook --execute EsercizioDatasetSklearn.ipynb --output EsercizioDatasetSklearn.executed.ipynb
```

### Compilazione in formato condivisibile
Per generare una versione HTML del notebook (utile per portfolio/review):
```bash
jupyter nbconvert --to html EsercizioDatasetSklearn.ipynb
```

## Pipeline Di Lavoro Implementata
1. Caricamento dataset da `apple_quality.csv`.
2. Analisi esplorativa iniziale (`info`, `describe`, distribuzione classi).
3. Pulizia e preparazione dati:
- arrotondamento a 2 decimali,
- rimozione della colonna identificativa `A_id`,
- encoding della target `Quality` (`bad -> 0`, `good -> 1`),
- standardizzazione delle feature numeriche.
4. Suddivisione train/test con `train_test_split`.
5. Addestramento e confronto modelli:
- `Perceptron`,
- `LogisticRegression`,
- `RandomForestClassifier`,
- `GaussianNB`.
6. Ottimizzazione iperparametri con `GridSearchCV`.
7. Feature selection con `RFECV`.
8. Valutazione tramite confusion matrix e curva ROC-AUC.
9. Selezione del modello migliore e salvataggio su file.

## Salvataggio E Riutilizzo Del Modello
Nel notebook il modello finale viene serializzato con Pickle nel file:
- `best_model.sav`

Il notebook mostra anche il caricamento del modello salvato e una verifica immediata delle prestazioni su `X_test`.

## Riproducibilita E Dipendenze
Per garantire la riproducibilita nel tempo, si consiglia di salvare le versioni dei pacchetti utilizzati:
```bash
pip freeze > requirements.txt
```

Successivamente, su un altro ambiente:
```bash
pip install -r requirements.txt
```

## Output Attesi
- metriche comparative dei modelli,
- confusion matrix,
- curva ROC con valore AUC,
- file serializzato del modello migliore (`best_model.sav`).

## Conclusioni
Questo progetto dimostra una pipeline completa di machine learning per la classificazione, partendo da un dataset reale, con tutte le fasi chiave: analisi, preparazione, addestramento, valutazione e salvataggio del modello.

## Note
- Il dataset `apple_quality.csv` è stato scaricato in modo gratuito da Kaggle, sito di riferimento per dataset pubblici.
- Il notebook è commentato in modo dettagliato per facilitare la comprensione di ogni fase.