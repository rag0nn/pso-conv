# pso_conv
<h1>Kanser Türleri Ayırt Etmek Amacıyla Parçacık Sürüsü Optimizasyonu Kullanılarak Konvolüsyonel (Evrişimli) Modelleri En Efektif Şeklide Eğitme</h1>

Bu repo parçacık sürüsü optimizasyonu ile bir konvolüsyonel nöral ağ eğitimi içeriyor.

Modeller Kaggle.com üzerindeki kanser türlerine ait görsel ve etiketler kullanılarak eğitildi.

Eğitilirken 10 iterasyonlu 3 parçacık içeren parçacık sürüsü, 100 iterasyonlu konvolüsyon ağları olarak toplamda 10 model oluşacak şekilde kullanıldı. Parçacıkların modeldeki konvolüsyon katmanlarındaki filtre sayı parametrelerini tutması amaçlandı.


Model:

    Conv2D(c1,kernel_size=(3,3),activation="relu", kernel_initializer=tf.keras.initializers.Constant(value=0.1)))
    
    MaxPooling2D(pool_size=(2,2)))
    
    (Conv2D(c2,kernel_size=(3,3),activation="relu", kernel_initializer=tf.keras.initializers.Constant(value=0.1)))
    
    (MaxPooling2D(pool_size=(2,2)))
    
    (Conv2D(c3,kernel_size=(3,3),activation="relu", kernel_initializer=tf.keras.initializers.Constant(value=0.1)))
    
    d(MaxPooling2D(pool_size=(2,2)))
    
    (Flatten())
    
    (Dense(7, kernel_initializer='glorot_uniform',activation="softmax"))
    
Diğer eğitim parametreleri:

    loss: Categorical Crossentropy,

    optimizer: Adam (0.001 lr. ile)
    
Modellerin f1, recall precision, accuracy değerlerini aşağıdaki grafiklerde görülebilir. Bu sonuçlardan yola çıkılarak optimal model tercih edilebilir.

<img src="https://github.com/rag0nn/pso-conv/blob/main/results/plot_2d_scored.jpg?raw=true" width="auto">
<img src="https://github.com/rag0nn/pso-conv/blob/main/results/plot_3d_egitim_acc.jpg?raw=true" width="auto">
<img src="https://github.com/rag0nn/pso-conv/blob/main/results/plot_3d_f1_acc.jpg?raw=true" width="auto">
<img src="https://github.com/rag0nn/pso-conv/blob/main/results/plot_3d_test_acc.jpg?raw=true" width="auto">
