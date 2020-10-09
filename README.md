# Lab 4

Random flip
    
    image = tf.image.random_flip_left_right(image)

Train-blue

Val-orange

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_1-acc.png)

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_1-loss.png)

Random rotation

    degree = 30
    degrand = np.random.uniform(-degree, degree)
    image = tfa.image.rotate(image, np.pi * degrand / 180, interpolation='BILINEAR')

Train-green

Val-grey

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_2-1-acc.png)

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_2-1-loss.png)

    degree = 60
    degrand = np.random.uniform(-degree, degree)
    image = tfa.image.rotate(image, np.pi * degrand / 180, interpolation='BILINEAR')

Train-blue

Val-pink

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_2-3-acc.png)

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_2-3-loss.png)

Random brightness&contrast

    image = tf.image.random_brightness(image, 0.5, seed=None)
    image = tf.image.random_contrast(image, 0.4, 1.2, seed=None)

Train-pink

Val-green

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_3-1-acc.png)

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_3-1-loss.png)

    image = tf.image.random_brightness(image, 0.7, seed=None)
    image = tf.image.random_contrast(image, 0.6, 1.2, seed=None)

Train-green

Val-grey

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_3-2-acc.png)

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_3-2-loss.png)

Gaussian noise

    noise_img = image + tf.random.normal(shape=tf.shape(image), mean=0.0, stddev=1.0, dtype=tf.float32)
    noise_img = tf.clip_by_value(noise_img, 0.0, 1.0)

Train-green

Val-grey

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_4-acc.png)

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_4-loss.png)

Optimal

    image = tf.image.random_flip_left_right(image)
    degree = 30
    degrand = np.random.uniform(-degree, degree)
    image = tfa.image.rotate(image, np.pi * degrand / 180, interpolation='BILINEAR')
    image = tf.image.random_brightness(image, 0.5, seed=None)
    image = tf.image.random_contrast(image, 0.4, 1.2, seed=None)
    with tf.name_scope('Add_gaussian_noise'):
        noise_img = image + tf.random.normal(shape=tf.shape(image), mean=0.0, stddev=1.0, dtype=tf.float32)
        noise_img = tf.clip_by_value(noise_img, -1.0, 1.0)

Train-grey

Val-orange

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3/Graphs/try2%20(why)/4_5.png)
