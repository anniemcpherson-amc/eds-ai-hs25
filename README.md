# Natural Language Processing with Disaster Tweets (Kaggle)

**EDS – AI HS25 Project (HSLU)**  
Autorin: **Annabelle McPherson**  
Relevanter Notebook: **disater_tweets**


Dieses Projekt beschäftigt sich mit der automatischen Klassifikation von Tweets in Bezug auf reale Katastrophenereignisse. Ziel ist es, vorherzusagen, ob ein Tweet tatsächlich eine **reale Katastrophe** beschreibt (`target = 1`) oder ob katastrophenbezogene Begriffe **metaphorisch / im übertragenen Sinn** verwendet werden (`target = 0`).  
Die Arbeit orientiert sich an der Kaggle-Challenge **“Natural Language Processing with Disaster Tweets”**. :contentReference[oaicite:1]{index=1}

---

## Problemstellung & Ziel

Soziale Medien liefern in Krisensituationen Informationen in Echtzeit, gleichzeitig enthalten viele Tweets Wörter wie *fire*, *flood* oder *explode*, ohne dass ein reales Ereignis gemeint ist. Daher wird ein Modell entwickelt, das Tweets zuverlässig in **„Katastrophe“** vs. **„keine Katastrophe“** klassifiziert. :contentReference[oaicite:2]{index=2}

**Evaluationsmetrik: F1-Score (Klasse 1 = Katastrophe)**  
Der F1-Score ist geeignet, weil **Precision und Recall gleichzeitig relevant** sind. In einem realen Einsatz sind insbesondere **False Negatives** kritisch, da echte Katastrophen übersehen würden. :contentReference[oaicite:3]{index=3}

---

## Datensatz

Der Datensatz stammt aus Kaggle und besteht aus Tweets mit optionalen Zusatzfeldern (`keyword`, `location`) sowie dem Label `target`. Im Projekt liegt der Fokus primär auf dem Textfeld `text`. :contentReference[oaicite:4]{index=4}

**Dateien:**
- `train.csv`
- `test.csv`

---

## Vorgehen & Methoden (5 Modelle)

Im Notebook werden fünf Ansätze implementiert und anhand des **F1-Scores für „Katastrophe“** verglichen. :contentReference[oaicite:5]{index=5}

1. **Baseline:** TF-IDF + Logistic Regression  
2. **Deep Learning:** Bi-LSTM mit vortrainierten **GloVe Embeddings** (frozen)  
3. **LLM Zero-Shot (API):** direkte Klassifikation ohne Training (mit Caching)  
4. **Embedding-basiert:** Sentence-Transformer **all-MiniLM-L6-v2** + Logistic Regression  
5. **LLM Few-Shot (API):** Klassifikation mit wenigen gelabelten Beispielen im Prompt (mit Caching) :contentReference[oaicite:6]{index=6}

Zusätzlich wird eine **Fehleranalyse (FP/FN)** durchgeführt und diskutiert, inklusive Hinweis auf mögliche **Label Noise** im Datensatz. :contentReference[oaicite:7]{index=7}

---

## Reproduzierbarkeit & Hinweise zu API

Die LLM-Abschnitte (Zero-Shot / Few-Shot) werden **nur ausgeführt**, wenn ein gültiger API-Key via Environment Variable vorhanden ist.  
Ist kein Key gesetzt, werden diese Schritte automatisch übersprungen, sodass das Notebook weiterhin ausführbar bleibt. :contentReference[oaicite:8]{index=8}

### API-Key setzen (lokal, nicht im Repo!)
```bash
export OPENAI_API_KEY="YOUR_KEY_HERE"
