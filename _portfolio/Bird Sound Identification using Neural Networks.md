---
title: "Bird Species Classification Using Neural Networks"
excerpt: "This project explores the application of neural networks in classifying bird species based on their sounds. Utilizing a dataset from Xeno-Canto with 10 audio clips for each of the 12 selected bird species, the study focuses on binary classification (amecro vs. norfli) and multi-class classification for all 12 species. Various neural network architectures, including convolutional neural networks (CNNs) and transfer learning with VGG16, are employed and evaluated. The report discusses encountered limitations, compares model performances, and emphasizes the potential of neural networks for bird species identification."
---
Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/Bird%20Sound%20Identification%20in%20Seattle%20Area).

## Introduction
Identification of bird species traditionally requires expertise. This project leverages machine learning, specifically neural networks, to classify species based on unique sound patterns. Binary and multi-class classification tasks are undertaken, addressing challenges of distinguishing between specific species and handling diverse characteristics. The dataset consists of 10 sound clips per species sourced from Xeno-Canto, recorded in the Seattle area.

### Dataset Description
The dataset includes original sound clips from Xeno-Canto, with 10 clips for each of the 12 bird species. Spectrograms generated from these clips serve as input for training the neural network.

### Problem Types
Binary classification focuses on distinguishing amecro and norfli, while multi-class classification involves all 12 species. This dual approach provides insights into different aspects of bird species classification, evaluating the performance of various neural network structures.

## Theoretical Background
### Neural Networks
Neural networks, inspired by the human brain, consist of interconnected nodes organized into layers. Various types, such as Feedforward Neural Networks (FNNs), Convolutional Neural Networks (CNNs), Recurrent Neural Networks (RNNs), and Long Short-Term Memory (LSTM) Networks, are employed based on the characteristics of the data.

### Compilation Techniques
Compilation involves configuring and optimizing the model before training. Choices like loss function, optimizer, and evaluation metrics significantly impact performance. Hyperparameters such as learning rate, batch size, and regularization techniques are carefully tuned for optimal results.

### Activation Function
Activation functions, like sigmoid and SoftMax, introduce non-linearity, enhancing the network's ability to learn complex patterns.

### Transfer Learning
Transfer learning leverages pre-trained models for new tasks, reducing data and computation requirements. This project employs VGG16 for audio classification.

### Spectrograms
Spectrograms visually represent frequency content over time, crucial for analyzing audio signals. They serve as input features for sound classification models.

## Methodology
### Data Preprocessing
Audio files undergo resampling, windowing, and spectrogram computation. Labels are one-hot encoded, and data is split into training and testing sets.

### Binary Classification
Two models, one with and one without dropout, are employed for distinguishing amecro and norfli.

### Multi-Class Classification
Sequential CNN models with and without dropout address the challenge of classifying all 12 bird species.

### Transfer Learning
Pre-trained VGG16 is adapted for audio classification, and model performance is evaluated.

## Computational Results
### Binary Classification
| Model                | Train Accuracy | Test Accuracy | Training Loss | Testing Loss |
|----------------------|----------------|---------------|---------------|--------------|
| Model 1              | 99.57%         | 99.16%        | 1.76%         | 1.78%        |
| Model 2 (with dropout)| 99.36%         | 99.16%        | 1.65%         | 1.75%        |

### Multi-Class Classification
| Model                | Train Accuracy | Test Accuracy | Training Loss | Testing Loss |
|----------------------|----------------|---------------|---------------|--------------|
| Model 1              | 90.95%         | 88.23%        | 31.15%        | 48.59%       |
| Model 2 (with dropout)| 92.22%         | 89.22%        | 26.28%        | 35.89%       |

### Transfer Learning
| Model                | Train Accuracy | Test Accuracy | Training Loss | Testing Loss |
|----------------------|----------------|---------------|---------------|--------------|
| VGG16                | 94.27%         | 92.94%        | 26.96%        | 32.54%       |

## Discussion
### Binary Classification
Both models performed well, with Model 2 showing potential benefits from dropout regularization. Overfitting concerns were mitigated, and generalization improved.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/df293604-7da9-4f87-b178-714217225be6)

We can see the validation loss is increasing with increase in epochs which may suggest overfitting.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/90a1c440-485a-4361-98e1-111a06534377)

We can see the loss of both the training and validation data is decreasing and the accuracy is increased. It may suggest Model 2's use of dropout regularization may help prevent overfitting and improve the model's generalization performance on unseen data.

### Multi-Class Classification
Model 2, with dropout, outperformed Model 1, demonstrating improved generalization. The confusion matrix indicated challenges in distinguishing specific classes, potentially due to similar spectrogram patterns.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/9b9cce80-1893-47c0-8b51-82e0278e8162)

We can see the validation loss is higher than the training loss which may suggest overfitting.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/73c0236f-cf6c-4776-a0f9-4675bbdb9044)

We can see model2 has much less loss which can suggest that the addition of the dropout layer has helped to reduce overfitting and improve the model's generalization ability

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/c791a522-a01e-4697-aaad-e06a3d1c1ec0)
![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/532c1425-0c27-4f6e-880d-76026604097a)

If we see the confusion matrix, most misclassified labels are labels of class 2 and class 8 are misclassified as class 6. 

0: amecron, 1: barswa, 2: bkcchi, 3: blujay, 4: daejun, 5: houfin, 6: mallar3, 7: norfli, 8: rewbla, 9: stejay, 10: wesmea, 11: whcspa

- So, bkcchi and rewbla are often misclassified as mallar3. Let us see the spectrogram and wave plots of these 3 birds audio clips.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/a56d9e6f-400f-447c-816a-8bd9ad634f23)

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/ffd742c7-f284-4c30-8126-57f7c2ecca13)

We can see few of the loud piches looks kind of similar and taking 2 second windows may give similar spectrograms leading to little noise and misclassifications in the model.

### Transfer Learning
VGG16 transfer learning achieved the highest accuracy, highlighting its effectiveness in audio classification tasks.

## Conclusion
In conclusion, the study focused on three different classification tasks: Binary Classification, Multi-Class Classification, and Transfer Learning, all of which aimed to classify different bird species based on their images or audio data. The study used various deep learning models such as CNN, Sequential CNN, and pre-trained VGG16, and evaluated their performance based on accuracy and loss metrics. The results showed that both binary classification models performed well on testing data, with Model 2 having a slight edge due to its use of dropout regularization. In multi-class classification, Model 2 with dropout performed significantly better than Model 1, indicating that dropout regularization can help improve the model's generalization ability. Lastly, the transfer learning approach using pre-trained VGG16 performed best with an accuracy of 92.94%, demonstrating the effectiveness of transfer learning in audio classification tasks. Overall, the study provided valuable insights into using deep learning techniques for bird species classification and provided a foundation for further research in the field.
