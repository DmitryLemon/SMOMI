Вторая лабораторная заключалась в том, чтобы попробовать обучить нейросеть с разными стартовыми параметрами: количеством слоев, количеством нейронов на слоях, шагом обучения.

1. Первая нейросеть:
  
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=32, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
  
  Метрики точности:
  
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/master/Lab2/first%20try/epoch_acc.png) !![Image alt](https://github.com/DmitryLemon/SMOMI/blob/master/Lab2/first%20try/epoch_val_acc.png)

  Функции потерь:
  
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/master/Lab2/first%20try/epoch_loss.png) ![Image alt](https://github.com/DmitryLemon/SMOMI/blob/master/Lab2/first%20try/epoch_val_loss.png)

2. Вторая нейросеть:

        tf.keras.layers.Conv2D(filters=16, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=4, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
        
  Метрики точности:
  

  Функции потерь:
  
3. Третья нейросеть:
  
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Conv2D(filters=8, kernel_size=3),
        tf.keras.layers.MaxPool2D(),
        tf.keras.layers.Flatten(),
        tf.keras.layers.Dense(NUM_CLASSES, activation=tf.keras.activations.softmax)
        
  Метрики точности:
  

  Функции потерь:
  
  
