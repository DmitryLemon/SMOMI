# Lab №1

В данной лабораторной работе мы запускаем свёрточную нейронную сеть с разным количеством свёрточных слоёв и фильтров в них для определения того, как это влияет на обучение нейронной сети.

Первый запуск - два слоя: 8 и 8 фильтров

tf.keras.models.Sequential([
        tf.keras.layers.Input(shape=(224,224,3)),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
    ])

Тренировочные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-train-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-train-loss.png)

Валидационные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-val-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-val-loss.png)


Второй запуск - три слоя: 8, 8 и 8 фильтров

tf.keras.models.Sequential([
        tf.keras.layers.Input(shape=(224,224,3)),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
    ])

Тренировочные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-8-train-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-8-train-loss.png)

Валидационные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-8-val-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-8-val-loss.png)

При добавлении слоя заметно, что скорость обучения нейронной сети снизилась, и точность возрастает медленнее, следовательно необходимо больше эпох для обучения сети

Третий запуск - три слоя: 16, 16 и 8 фильтров

tf.keras.models.Sequential([
        tf.keras.layers.Input(shape=(224,224,3)),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
    ])

Тренировочные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-8-train-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-8-train-loss.png)

Валидационные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-8-val-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-8-val-loss.png)

При увеличении количества фильтров в первых двух слоях скорость обучения сети возросла

Четвёртый запуск - четыре слоя: 64, 32, 16 и 8 фильтров

tf.keras.models.Sequential([
        tf.keras.layers.Input(shape=(224,224,3)),
        tf.keras.layers.Conv2D(filters=64, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=32, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
    ])

Тренировочные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-16-32-8-train-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-16-32-8-train-loss.png)

Валидационные данные:
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-16-32-8-val-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-16-32-8-val-loss.png)

Вывод: При добавлении слоёв в свёрточную нейронную сеть 
