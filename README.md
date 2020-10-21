# Lab 4

Random flip
    
    image = tf.image.random_flip_left_right(image)

Train-orange


![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_1-tror.png)

Random rotation

    degree = 15
    degrand = np.random.uniform(-degree, degree)
    image = tfa.image.rotate(image, np.pi * degrand / 180, interpolation='BILINEAR')

Train-blue


![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_2-15-trbl.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_2-15-trgr.png)

    degree = 30
    degrand = np.random.uniform(-degree, degree)
    image = tfa.image.rotate(image, np.pi * degrand / 180, interpolation='BILINEAR')
    
Train - green

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_2-30-trgr.png)


    degree = 45
    degrand = np.random.uniform(-degree, degree)
    image = tfa.image.rotate(image, np.pi * degrand / 180, interpolation='BILINEAR')

Train-blue

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_2-45-trbl.png)

Random brightness&contrast

    image = tf.image.random_brightness(image, 0.1, seed=None)
    image = tf.image.random_contrast(image, 0.7, 1.4, seed=None)

Train-blue

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_3-2-trbl.png)

    image = tf.image.random_brightness(image, 0.3, seed=None)
    image = tf.image.random_contrast(image, 0.5, 1.5, seed=None)

Train-red

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_3-2-trrd.png)

    image = tf.image.random_brightness(image, 0.5, seed=None)
    image = tf.image.random_contrast(image, 0.3, 1.7, seed=None)
    
Train - orange

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_3-3-tror.png)


Gaussian noise

    noise_img = image + tf.random.normal(shape=tf.shape(image), mean=0.0, stddev=1.0, dtype=tf.float32)
    noise_img = tf.clip_by_value(noise_img, -1.0, 1.0)

Train-pink

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_4-trpn.png)

    noise_img = image + tf.random.normal(shape=tf.shape(image), mean=0.0, stddev=0.25, dtype=tf.float32)
    
Train-blue

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_4-25.png)

    noise_img = image + tf.random.normal(shape=tf.shape(image), mean=0.0, stddev=0.25, dtype=tf.float32)
    
Train-blue

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_4-10.png)


Optimal

    image = tf.image.random_flip_left_right(image)
    degree = 30
    degrand = np.random.uniform(-degree, degree)
    image = tfa.image.rotate(image, np.pi * degrand / 180, interpolation='BILINEAR')
    image = tf.image.random_brightness(image, 0.5, seed=None)
    image = tf.image.random_contrast(image, 0.3, 1.7, seed=None)
    with tf.name_scope('Add_gaussian_noise'):
        noise_img = image + tf.random.normal(shape=tf.shape(image), mean=0.0, stddev=0.25, dtype=tf.float32)
        noise_img = tf.clip_by_value(noise_img, -1.0, 1.0)

Train-blue, red

![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_5-1.png)
![Image alt](https://github.com/DmitryLemon/SMOMI/blob/lab3try2/Graphs/4_5-2.png)
