# Blood Cells Classification

## Dataset- Blood Cell Images

This dataset contains 12,500 augmented images of blood cells with accompanying cell type labels . There are approximately 3,000 images for each of 4 different cell types grouped into 4 different folders (according to cell type). 
The cell types are Eosinophil, Lymphocyte, Monocyte, and Neutrophil. This dataset is accompanied by an additional dataset containing the original 410 images as well as two additional subtype labels and also bounding boxes for each cell in each of these 410 images.
 The folder 'dataset2-master' consists of 2,500 augmented images as well as 4 additional subtype labels.

## Blood Cell Classes
![classes](https://user-images.githubusercontent.com/73905298/110814496-80fec500-82af-11eb-8b07-c62aaa33847b.jpg)


## Model Summary 

Layer (type)                 Output Shape              Param 

conv2d_48 (Conv2D)           (None, 198, 198, 16)      448       
_________________________________________________________________
max_pooling2d_48 (MaxPooling (None, 99, 99, 16)        0         
_________________________________________________________________
batch_normalization_9 (Batch (None, 99, 99, 16)        64        
_________________________________________________________________
conv2d_49 (Conv2D)           (None, 97, 97, 64)        9280      
_________________________________________________________________
max_pooling2d_49 (MaxPooling (None, 48, 48, 64)        0         
_________________________________________________________________
dropout_48 (Dropout)         (None, 48, 48, 64)        0         
_________________________________________________________________
conv2d_50 (Conv2D)           (None, 46, 46, 64)        36928     
_________________________________________________________________
max_pooling2d_50 (MaxPooling (None, 23, 23, 64)        0         
_________________________________________________________________
dropout_49 (Dropout)         (None, 23, 23, 64)        0         
_________________________________________________________________
conv2d_51 (Conv2D)           (None, 21, 21, 64)        36928     
_________________________________________________________________
max_pooling2d_51 (MaxPooling (None, 10, 10, 64)        0         
_________________________________________________________________
dropout_50 (Dropout)         (None, 10, 10, 64)        0         
_________________________________________________________________
conv2d_52 (Conv2D)           (None, 8, 8, 64)          36928     
_________________________________________________________________
max_pooling2d_52 (MaxPooling (None, 4, 4, 64)          0         
_________________________________________________________________
dropout_51 (Dropout)         (None, 4, 4, 64)          0         
_________________________________________________________________
conv2d_53 (Conv2D)           (None, 2, 2, 128)         73856     
_________________________________________________________________
max_pooling2d_53 (MaxPooling (None, 1, 1, 128)         0         
_________________________________________________________________
dropout_52 (Dropout)         (None, 1, 1, 128)         0         
_________________________________________________________________
flatten_8 (Flatten)          (None, 128)               0         
_________________________________________________________________
dense_24 (Dense)             (None, 128)               16512     
_________________________________________________________________
dropout_53 (Dropout)         (None, 128)               0         
_________________________________________________________________
dense_25 (Dense)             (None, 64)                8256      
_________________________________________________________________
dropout_54 (Dropout)         (None, 64)                0         
_________________________________________________________________
dropout_54 (Dropout)         (None, 4)                 260

=================================================================
Total params: 219,460
Trainable params: 219,428
Non-trainable params: 32
_________________________________________________________________

The above Convolutional Neural Network classifies the 4 classes of blood cells- Eosinophils, Monocytes, Lymphocytes and Basophiles after training.
This model has 6 convolution layers, 2 dense layers, 7 dropouts and approximately 220K parameters.
It gives 80% and 79% accuracy for 20 epochs.

## Accuracy Incremention

Following methods were using in the above model to increase accuracy:
Increased the number of convolution layers from 2 to 6 which caused a  significant increase in accuracy.

Decreased the number of neurons in the convolution layers and connecting layers which led to a huge increase in accuracy %

The model started overfitting so we added Dropouts to the convolution layers and decreased the Dropout values from 0.7 and 0.5 to values of 0.4 and 0.3 in the connecting layer. 

## Model Evaluation


Accuracy	 

![accuracy](https://user-images.githubusercontent.com/73905298/110814809-d044f580-82af-11eb-8cc5-698b497e984d.jpg)

Loss

![loss](https://user-images.githubusercontent.com/73905298/110814818-d33fe600-82af-11eb-9f7d-57bb4f6ffd65.jpg)



