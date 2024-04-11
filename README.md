# Классификатор услуг

## Цель работы
Создать эффективный классификатор услуг, который на основании названия услуги сможет правильно присвоить соответствующую категорию услуги.

## Описание данных
Датасет, содержащий название услуги в LPU(Лечебно- профилактические учреждения), а так же категорию.

Описание полей:

- Название: Название услуги
- Категория: Категория услуги


## Этапы проведения работы
- EDA
- Обучение модели TF-IDF + CatBoostClassifier
- Обучение трансформера
- Подготовка отчета

## Навигация

| Наименование  | Описание      |
| ------------- | --------------|
| [1. pandas_profiling_report](https://html-preview.github.io/?url=https://github.com/yana-sklyanchuk/services_classifier/blob/main/pandas_profiling_report.html) | Общий обзор исследованных данных|
| [2. EDA_report](EDA_report.ipynb)|Итоги ознакомления с данными|
| [3. catboost_model](catboost_model.ipynb)|Обучение модели TF-ID-CatBoostClassifier|
| [4. category_classification](category_classification.ipynb)|Обучение трансформена|
| [5. final_report](final_report.ipynb)|Отчет|


## Лучшая метрика
Предложен классификатор услуг на основе доработанной версии distilbert-base-uncased, способный проводить классификацию названий услуг.


На оценочном наборе модель достигает следующих результатов:
- Loss: 0.1774
- Accuracy: 0.9490

Во время обучения использовались следующие гиперпараметры:
- learning_rate: 2e-05
- train_batch_size: 16
- eval_batch_size: 16
- seed: 42
- optimizer: Adam with betas=(0.9,0.999) and epsilon=1e-08
- lr_scheduler_type: linear
- num_epochs: 3


Training results



| Training Loss | Epoch | Step | Validation Loss | Accuracy |
|:-------------:|:-----:|:----:|:---------------:|:--------:|
| 0.5964        | 1.0   | 216  | 0.3048          | 0.9015   |
| 0.2687        | 2.0   | 432  | 0.1945          | 0.9432   |
| 0.1787        | 3.0   | 648  | 0.1774          | 0.9490   |


Framework versions


- Transformers 4.38.2
- Pytorch 2.2.1+cu121
- Datasets 2.18.0
- Tokenizers 0.15.2

