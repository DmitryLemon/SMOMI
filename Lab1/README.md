В этой задаче используется полносвязная нейронная сеть из шести слоев: один Flatten и пять Dense. Используется функция активации relu. В слоях Dense 512, 256, 128, 64 и 32 нейронов соответсвенно.

В цикле обучения используется оптимизатор adam, функция потерь SparseCategoricalCrossentropy и метрика accuracy. Всего производится 30 эпох обучения.

Функции потерь

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/master/Lab1/epoch_loss.png)

Метрики точности

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/master/Lab1/epoch_acc.png)

Оранжевым цветом обозначен график train, синим - график test.

Итоговая точность на тестовых данных: 0.5048
