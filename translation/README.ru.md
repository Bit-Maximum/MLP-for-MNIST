# 🧠 Классификация рукописных цифр с помощью MLP (MNIST)

[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/Bit-Maximum/MLP-for-MNIST/blob/main/README.md)
[![ru](https://img.shields.io/badge/lang-ru-blue.svg)](https://github.com/Bit-Maximum/MLP-for-MNIST/blob/main/translation/README.ru.md)

### 👤 Меркурьев Максим Андреевич  
🏫 *Дальневосточный федеральный университет, 2025*

---

## 📌 Описание проекта

Данный проект посвящён **изучению многослойных персептронов (MLP)** на примере классификации изображений из стандартного набора **MNIST**. Основная цель — изучение влияния параметров обучения (размера батча и числа эпох) на качество модели.

🔗 **Colab-версия проекта:**  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Z_qKQ3iwa7Gzs59P3HLrLoxs9qHRQE_a?usp=sharing)

Также возможен запуск локально через JupyterLab.

---

## 📊 О MNIST

MNIST — один из самых известных датасетов в машинном обучении. Он содержит:

- `60 000` изображений для обучения
- `10 000` изображений для тестирования
- Каждое изображение: `28×28` пикселей в оттенках серого
- Метки: от `0` до `9` — цифры, изображённые на картинке

Пример изображений MNIST:

![MNIST Demo](media/MNIST.png)

---

## 🧠 Что такое MLP?

**MLP (Multilayer Perceptron)** — это тип нейронной сети прямого распространения, состоящий из полностью связанных слоёв. Архитектура для этого проекта:

1. **Входной слой:** преобразует 28×28 → 784 признака
2. **Скрытые слои:**
    - 1 слой: 64 нейрона + ReLU
    - 2 слой: 64 нейрона + ReLU
3. **Выходной слой:** 10 классов (0–9) + Softmax

> Обучение осуществляется с помощью **градиентного спуска** и обратного распространения ошибки.

---

## 📌 Структура обучения

- 📥 **Предобработка данных**: flatten + нормализация
- 🔄 **Прямой проход** через слои (Feedforward)
- 🧮 **Функция потерь**: `CrossEntropy`
- 🧪 **Оценка точности** на тестовой выборке
- 📈 **Графики**: потерь и точности в зависимости от эпох и батча

---

## 📦 Установка (для запуска локально)

1. Клонируйте репозиторий:
```bash
git clone https://github.com/Bit-Maximum/MLP-for-MNIST.git
cd MLP-for-MNIST
```

2. Установите зависимости:
```bash
pip install -r requirements.txt
```

3. Запустите проект:
```bash
jupyter lab run.ipynb
```

---

## 📉 Результаты
### 📌 После обучения модель достигла:
* Точности: `97.64%`
* Высокой устойчивости к переобучению
* Стабильного поведения при разных размерах батча и эпохах

### 📊 Были построены графики:
* Зависимость потерь от эпох
* Изменение точности на обучающей и тестовой выборках

![Accuracy vs Epochs for different batch sizes on test data](media/Accuracy vs Epochs for different batch sizes on test data.png)

![Final Accuracy vs Batch Size](media/Final Accuracy vs Batch Size.png)

![Test Accuracy Heatmap](media/Test Accuracy Heatmap.png)

![t-SNE (Not Trained)](media/t-SNE Not Trained.png)

![t-SNE (Epoch 20)](media/t-SNE.png)

## 📚 Теоретическая база
Проект охватывает:
* Основы архитектуры MLP
* Принцип работы ReLU и Softmax
* Механизмы SGD и обратного распространения
* Практическое применение MLP к задаче классификации изображений
