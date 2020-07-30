# CIFAR10

## Preprocessing

- The data has been scaled by using MinMaxScaler.
- Other scaling functions were also used such as Robust Scaler and MinMaxScaler, but Standard Scaling performed best.

## Output Layer

- For output optimizer used is 'adam'(mentioned).
- 'categorical crossentropy' is used as loss function because it is multi-class problem and hence we cannot use binary crossentropy.

## Change in Layers and Neurons

- Following is the table of change in number of layer and its corresponding obtained accuracies

| Layers | Neurons per Layer | Training accuracy | Validation Accuracy |
| --- | --- | --- | --- | 
| 2 | 512 | 31 | 41 |
| 2 | 1024 | 35 | 44 |
| 3 | 512 | 40 | 46 | 
| 3 | 1024 | 45 | 45 | 
| 4 | 512 | 50 | 50 | 
| 4 | 1024 | 55 | 58 | 

## MLP vs CNN

- From the results we can clearly see that CNN performs much better than MLP.
- The main disadvantage of MLP is that as the number of total parameters grows to very high. This is inefficient because there is redundancy in such high dimensions.
- Another reason why CNN outperforms MLP is because of convolution and pooling layer that CNN has.
- Convolutional layers take advantage of the local spatial coherence of the input. This is only possible because we assume that spatially close inputs are correlated. For images, this can be seen by the fact that the image loses its meaning when the pixels are shuffled.
- Using this property, CNNs are able to cut down on the number of parameter by sharing weights. This makes them extremely efficient in image processing, compared to multi-layer perceptrons.

## Plots

- Below are graphs of Loss and Accuracies of CNN1 and CNN2.

Loss | Accuracy
- | - 
![alt text](CNN1.png "Title") | ![alt text](CNN1_.png "Title")
![alt text](CNN2.png "Title") | ![alt text](CNN_.png "Title")

- From figure it is clearly visible that as number of epochs increases , training loss decreases and thus training accuracy increases.
- In case of CNN1, although training loss decreases , the validation loss keeps on increases.
- The reason for this is CNN1 does have any 'dropout', this causes the model to be over fitting, that is just memorizing the training data.
- In general a overfitting model can be improved by adding dropout, which is added in CNN2. Hence, it is clearly visible that in CNN2 training loss decreases and also the validation loss decreases.
- Hence, for CNN2 the training as well as validation accuracy both increases with number of epochs due to dropout.
- Increasing the epochs might increase the accuracy, but not necessarily it means that MORE epochs means MORE accuracy, it may cause model to overfit. We can add early stopping to check if number of epochs are appropriate without overfitting.


## Improvement

- We can improve model by following ways
    - add noise to dense or convolution layers
    - add drop-out layers
    - add l1 or l2 regularizers
    - add early stopping
    
    
