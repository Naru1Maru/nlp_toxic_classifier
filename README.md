## 🧠 Russian Toxic Classifier with Explainable Predictions

Классификатор токсичных комментариев на русском языке, основанный на модели `cointegrated/rubert-tiny`. Модель дообучена на объединённом корпусе с участием датасета `PolyGuardMix`, `ru-merged-toxic-comments` и вручную собранных комментариев из ВКонтакте.

---

### 🔍 Кратко о проекте

* **Цель**: бинарная классификация комментариев (токсичный / не токсичный)
* **Особенности**:

  * Использована модель `cointegrated/rubert-tiny`, дообученная с перекрёстной валидацией (5 фолдов)
  * Сравнение с другими моделями (`distilbert-base-multilingual-cased`, `DeepPavlov/rubert-base-cased`)
  * Визуализация ошибок и использование explainable AI (IG-атрибуции)
  * Отчёт с метриками, графиками ROC-кривой и матрицей ошибок

---

### 📊 Сравнение моделей

| Модель                  | Accuracy  | F1        | ROC AUC   | Brier     |
| ----------------------- | --------- | --------- | --------- | --------- |
| **RuBERT‑tiny (наша)**  | **0.888** | **0.894** | **0.962** | **0.083** |
| DistilBERT‑multilingual | 0.796     | 0.707     | 0.576     | 0.234     |
| DeepPavlov RuBERT‑base  | 0.215     | 0.103     | 0.444     | 0.278     |

> ⚠️ В ВК-датасете разметка не всегда точная (не вручную проверена полностью)

---

### 📁 Основные файлы

* `notebooks/train_and_evaluate.ipynb` — обучение и метрики
* `src/xai_utils.py` — объяснение предсказаний
* `outputs/` — готовые ROC-кривые и матрицы ошибок
* `requirements.txt` — зависимости

---

### 🚀 Быстрый запуск

```bash
git clone https://github.com/Naru1Maru/nlp_toxic_classifier
cd nlp_toxic_classifier
pip install -r requirements.txt
jupyter notebook notebooks/train_and_evaluate.ipynb
```

---
