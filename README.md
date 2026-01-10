# Natual Language Processing with Disater Tweets
EDS – AI HS25 project

Dieses Projekt beschäftigt sich mit der automatischen Klassifikation von Tweets
in Bezug auf reale Katastrophenereignisse. Ziel ist es, vorherzusagen, ob ein Tweet
tatsächlich eine Katastrophe beschreibt oder nicht.

Das Projekt orientiert sich an der Kaggle-Challenge  
**“Natural Language Processing with Disaster Tweets”**  
und dient als praxisnahe Anwendung von Methoden aus dem Bereich
Natural Language Processing, Machine Learning und Deep Learning.

--

## Projektziel

Ziel des Projektes ist es, 
- eine **solide und nachvollziehbare Baseline** zu entwickeln,
- deren **Stärken und Schwächen systematisch zu analysieren**,
- darauf aufbauend **klassische Deep-Learning-Modelle** einzusetzen,
- und abschliessend einen **modernen Transformer-Ansatz** zu evaluieren.

Als zentrale Bewertungsmetrik wird der **F1-Score** verwendet, da er ein ausgewogenes Verhältnis zwischen Precision und Recall beitet und für unbalancierte KLassifikationsprobleme besonders geeignet ist. 

--

## Datensatz

Der verwendete Datensatz stammt aus der Kaggle.Challenge und besteht aus Tweets, die manuell als *Katastrophe* oder *keine Katastrophe* gelabelt wurden. 

Verwendete Dateien:
- 'train.csv'
- 'test.csv'

Die Texte enthalten kurze, informelle Sprache, Hashtags, URLs, Mehrdeutigkeiten sowie metaphorische Ausdrücke, was die Klassifikation inhaltlich anspruchsvoll macht. 

--

## Projektstruktur

eds-ai-hs25/
│
├── data/
│ ├── train.csv
│ ├── test.csv
│ └── glove/
│ └── glove.6B.100d.txt (nicht im Repository enthalten)
│
├── disaster_tweets_baseline.ipynb
├── README.md
└── .gitignore

**Hinweis:** Vortrainierte Embedding und Transformer-Modelle sind aufgrund ihrer Grösse nicht im Repositotry enthalten. 

--

## Methodik & Projektphasen 

### Tag 1: Baseline & Projekt-Setup
- Textrepräsentation mittel TF-IDF
- Klassifikation mit Logistic Regression
- Evaluation anhand von:
  - F1 - Score
  - Precision & Recall
  - Confusion Matrix
Die Baseline liefert eie robuste Ausgangsbasis und ermöglicht einen klaren Referenzpunkt für alle weiteren Modelle.

### Tag 2: Fehleranalyse & Zusatzanalysen 
- Systematische Analyse von:
  - False Positives
  - False Negatives
- Untersuchung konkreter Tweet-Beispiele
- Zusatzanalyse: Textlänge vs. Modellperformance
Die Ergebnisse zeigen, dass Modellfehler nicht durch einfach strukturelle Merkmale erklärbar sind, sondern primär durch fehlendes semantisches Kontextverständnid entstehen

## Tag 3: Klassische Deep Leaerning (Bi-LSTM + GloVe)
- Tokenisierung und Padding der Texte
- Verwendung vortrainierter GloVe-Embeddings (100 Dimensionen)
- Einsatz eines bidirektionalen LSTM-Netzwerkes
- Vergleich der Performance mit der TF-IDF-Baseline
Das Bi-LSTM-Modell verbessert insbesondere die Erkennung kontextabhängiger Formulierungen, geht jedoch mit höher Rechenkomplexität einher.

## Tag 4: Transformer-Ansatz (DistilBERT / BERTweet)
- Einsatz ein Transformer-Modells als Stats-Of_........
- FERTIG MACHEN WENN TAG 4 GEMACHT IST!!!!!!

---

## GloVe Embeddings

Für das Bi-LSTM-Modell werden vortrainierte GloVe-Embeddings verwendet: 
- **Quelle:** Stanford NLP
- **Version:** 'glove.6B.100d.txt'

Download: 
https://nlp.stanford.edu/projects/glove

Ablagepfad:
data/glove/glove.6B.100d.txt

--

## Fazit

odINVJoi gjihj oihf ijh adf uz d  hwdg f

--

## Autorin 

Annabelle McPherson
BSc Data Science / AI Project
Hochschule Luzern
