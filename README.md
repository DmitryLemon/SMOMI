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

Тренировочные данные - серый
Валидационные данные - оранжевый

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-loss.png)



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

Тренировочные данные - 
Валидационные данные - 

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-8-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-8-8-loss.png)


При добавлении слоя заметно, что скорость обучения нейронной сети снизилась, и точность возрастает медленнее, необходимо больше эпох для обучения сети

Третий запуск - три слоя: 8, 16 и 16 фильтров

        tf.keras.models.Sequential([
        tf.keras.layers.Input(shape=(224,224,3)),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
        ])

Тренировочные данные - оранжевый
Валидационные данные - синий

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-16-16-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-8-16-16-loss.png)


При увеличении количества фильтров в первых двух слоях скорость обучения сети возросла


Четвёртый запуск - четыре слоя: 16, 16, 8 и 8 фильтров

        tf.keras.models.Sequential([
        tf.keras.layers.Input(shape=(224,224,3)),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
        ])

Тренировочные данные - синий
Валидационные данные - розовый

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-8-8-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-8-8-loss.png)

И снова, при добавлении свёрточного слоя скорость обучения сети упала

Пятый запуск - четыре слоя: 16, 16, 32 и 32 фильтров

        tf.keras.models.Sequential([
        tf.keras.layers.Input(shape=(224,224,3)),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=32, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=32, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
        ])

Тренировочные данные - розовый
Валидационные данные - зелёный

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-32-32-acc.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab1/Lab1/Graphics/NN-16-16-32-32-loss.png)

Сеть достигла большей точности за меньшее число эпох по сравнению с предыдущей сетью


Вывод: При добавлении свёрточных слоёв в свёрточную нейронную сеть без изменения количества фильтров скорость обучения сети уменьшается. Если же увеличивать количество фильтров без изменения количества свёрточных слоёв, то скорость обучения сети увеличивается
