# 🚀 Система поиска изображений по текстовому запросу

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-orange)
![Transformers](https://img.shields.io/badge/Transformers-4.30%2B-critical)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-orange)
![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-green)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3%2B-yellow)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7%2B-red)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12%2B-lightgrey)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-yellowgreen)

## 🎯 Цель проекта
Разработать демонстрационную версию системы поиска изображений по текстовому запросу с использованием мультимодальной нейронной сети, которая оценивает степень соответствия текста и изображения (0–1).  
Модель обучается на векторных представлениях изображений (ResNet-18) и текстов (BERT), предсказывает схожесть.

## 📌 Задачи
1) Провести исследовательский анализ данных:
   - Оценить качество разметки (эксперты + краудсорсинг)
   - Удалить дубликаты, некорректные и юридически неподобающие изображения
2) Подготовить векторные представления:
   - Векторизовать изображения (train_img.pkl / test_img.pkl)
   - Векторизовать тексты через BERT (train_text.npy)
   - Нормализовать векторы
3) Построить и обучить нейронную сеть на комбинированной оценке (0.9·expert + 0.1·crowd)
4) Реализовать поиск:
   - Функция search_and_display() с фильтрацией неподобающих запросов
5) Достичь приемлемого качества ранжирования на тестовом наборе

## 🔍 Описание данных
- **train.csv** -- наборы изображение-текст, до 5 описаний на каждое изображений
- **CrowdAnnotations.tsv** – краудсорс-оценки (доля оценивших как соответствующие изображений)
- **ExpertAnnotations.tsv** – экспертные оценки (4 балльная шкала) от 3 экспертов
- **test_queries.csv** – тестовые запросы
- **test_images/** – папка с тестовыми изображениями
- **train_images/** – папка с тренировочными изображениями

- Сформированы готовые вектора: **train_img.pkl**, **test_img.pkl**, **train_text.npy**

## 🛠 Технологический стек
- **Анализ данных**: Pandas, NumPy
- **Визуализация**: Matplotlib, Seaborn
- **ML/DL**: Scikit-learn, PyTorch, Transformers, torchvision
- **Векторизация**: ResNet-18 (ImageNet weights), BERT
- **Другие**: Jupyter Notebook, tqdm, pickle, Git

## 📂 Структура проекта
ImageTextML/\
├── notebook.ipynb              # Тетрадка с проектом\
├── train_img.pkl               # Векторизованные тренировочные изображения (ResNet-18)\
├── test_img.pkl                # Векторизованные тестовые изображения (ResNet-18)\
├── train_text.npy              # Векторизованные тренировочные тексты (BERT)\
├── README.md                   # Этот файл\
├── requirements.txt            # (опционально) зависимости\
└── data/                       # (не в репозитории) исходные данные

## 🏆 Ключевые метрики
- **RMSE**: 0.2100

> Качество ограничено сильным дисбалансом разметки (много несоответствий изображений своим описаниям).  
> Модель быстро переобучается, требуется больше позитивных пар или другая архитектура.

## 📞 Контакты
- Автор: Алексей Рудницкий
- Email: almax1024@gmail.com
- Telegram: @torward1024