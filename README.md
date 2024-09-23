# Pneumonia_X-Ray_Analysis
![xray](https://github.com/user-attachments/assets/0d410063-3f9a-41b6-aa96-32d5c1e8d916)
## Overview
The following analysis takes a deeper dive into the research and understanding behind pneumonia. This sickness being an inflammatory condition of the lungs that fills the air sacks with pus and other liquids due to an infection caused by fungi, bacteria, or a virus. Pneumonia can lead to complications like respiratory failure, sepsis, and lung abscesses, especially in high-risk groups such as children, the elderly, and people with lung complications. With that in mind, early detection of pneumonia is crucial according to medical experts. This analysis does just that by taking a deeper look into various x-rays of children between ages of one and five, taken by Guangzhou Women and Children’s Medical Center and determining if the given x-ray image match to that of a person with pneumonia of not.
## Business Problem
With all this into consideration, our stakeholders, Guangzhou Women and Children’s Medical Center, are requesting for a model to be made that can be used to appropriately distinguish the difference between x-rays classified as "NORMAL" and "PNEUMONIA" in order to continue their efforts in combatting this sickness.
## Data Understanding
The [data](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia?resource=download) provided by the stakeholders, consists of 5,863 x-rays. All divided into two classes, patients with pneumonia and normal patients. This data is already slpit into three different groups/folders. The first group being for the training sample; 5,216 images. The second being for testing, with 624 images. And the last being for validation, consisting of only 16 x-ray images.
### Normal Patient
![Screenshot 2024-09-23 124613](https://github.com/user-attachments/assets/043d171f-0460-4302-a9a3-1aad4064a3c0)
### Patient with Pneumonia
![Screenshot 2024-09-23 124958](https://github.com/user-attachments/assets/3275e957-a3e4-4933-935e-c5dfdd54b769)
## Modeling
### Model 1: Baseline Model/ Densely Connected Neural Network
Build a baseline densely connected network with two hidden layers and an output layer. The first two layers have ReLU activation, which introduces non-linearity to the model. The final layer uses a sigmoid activation function, which produces a probability output between 0 and 1 for binary classification.


![Screenshot 2024-09-23 143215](https://github.com/user-attachments/assets/452fc4d2-0e7f-4d8e-90e2-5a97011c16e1)
![Screenshot 2024-09-23 143230](https://github.com/user-attachments/assets/8598d07d-694d-478d-9130-5715e98e1c6b)

The first model had a validation accuracy of 62 percent and a training accuracy of 87 percent. One can infer that this densely connected neural network has a poor performance due to the poor validation score; validation loss of 1.04. The training loss and validation loss have a large gap between thhem of approximately 0.76. Another sign of overfitting is that the curves diverge in different directions.
### Model 2: Convolutional Neural Network

The second model being built is a convolutional neural network (cnn) model. The model will have two convolutional layers to extract feautures from the images, followed by max pooling layers, and a final fully connected layer to perform the classification.


![Screenshot 2024-09-23 145340](https://github.com/user-attachments/assets/bb9c3020-9b63-45ef-855f-3414f1d5b2f6)
![Screenshot 2024-09-23 145356](https://github.com/user-attachments/assets/ab97d762-0f0d-4f02-914d-45f94c118ef0)

The second model preformed much better than the first model. With a training loss of 0.16 and training accuracy of 0.93. As well as a validation loss of 0.29 and validation accuracy of 0.93. This model seems to have also delt with some of the overfitting. This can be seen through there being a small margin between the training loss and validation loss (approx. 0.13) and the curves are no longer diverging at the ends of the graph.
### Model 3: CNN Model Tuning with More Layers

Seeing that the convolutional neural network had a very good performance, the third model will expand on it and attempt to refine it by adding more layers to it. This will be done by adding more convolutional layers as well as more dense layers.
![Screenshot 2024-09-23 145957](https://github.com/user-attachments/assets/241dd339-137e-464b-860b-73ff392facf7)
![Screenshot 2024-09-23 150018](https://github.com/user-attachments/assets/34541530-680b-4250-931f-65ca112008e6)

This model had a very high training accuracy with a score of 0.99 and a training loss of barely 0.01. It also had a validation accuracy of 0.87 and validation loss of 0.31. This is also a well performing model as it seems that both curves trend in the same direction. The gap between the training loss and validaation loss is that of approx. 0.3.
### Model 4: CNN Tuning with Layers, Dropout, & Regularization

In this fourth model, the original CNN model will be tuned and refined even more in an attempt to further improve it. This time around adding the extra layers plus dropout layers with a rate of 0.25, L1 and L2 regularization with a factor of 0.01. All this in an attempt to further improve the training and validation scores as well as reducing the overfitting.
![Screenshot 2024-09-23 151130](https://github.com/user-attachments/assets/50533340-b478-4f9e-8d4e-9d12538b8fc8)
![Screenshot 2024-09-23 151148](https://github.com/user-attachments/assets/3537a7ac-213b-42a6-a917-c54b1e4dbc4c)

The results for the fourth model are poor. Reporting back a training accuracy of 0.74 and validation accuracy of 0.5. And a training loss of 1.0 and validation loss of 1.32. The results are most likely attributed to the extra layers and tuning causing the model to be too complex and overfitted instead of fixing the overfitting. Most likey attributed to too much tuning and not enough data.
## Evaluation
The best performing model out of the four models created was Model 2: Convolutional Neural Netwroks Model. For that reason, the model was used for the testing dataset. Reporting back a 0.41 test loss and a test accuracy of 0.81. With all this is mind, predictions were generated using that model.
![Screenshot 2024-09-23 151929](https://github.com/user-attachments/assets/5c2eaafb-b668-42bf-8cde-a625656c4adf)

A classification report was then called upon the predictions generated by this model and it came back with an f1-score of 0.86, precision of 0.79, and recall of 0.95. The recall score of 0.95 for the "PNEUMONIA" class means that the model correctly identified 95% of the actual pneumonia cases in the dataset. This indicates a high sensitivity of the model in detecting pneumonia, as it has a low likelihood of missing positive cases.
## Conclusion
This analysis consisted of attempting to successfullfy build the most efficient model for image classification. Ultimately the best performing model recommended for the Guangzhou Women and Children’s Medical Center to use in their attempt to helping detect pneumonia in patient x-rays would be the convolutional neural network model as it yielded the best results. This model coming with a recall score for sick patients of 0.95. Meaning that there is a 95% chance that this model will correctly be able to identify a person that is testing positive for pneumonia (true positive). Although the recall score for normal patients didnt come back as high as one would desire (true negatives), this is something that can often occur when making these models. However, it is more important to correctly identify a sick person correcly and try to minimize as many false positives as possible in this situation. This is because it is more harmful for a sick person to walk out not knowing that they have pneumonia and not be given treatment, than for a normal person who is fine to mistakenly be told that they have tested positive and still be given treatment even though they are fine. To further improve this model, more samples of different x-rays could be collected or one could further try different methods to tune this model. To further test this model, the Guangzhou Women and Children’s Medical Center could share this model with other hospitals and clinics to see how well the model performs for them.
![lungs](https://github.com/user-attachments/assets/abe7ece2-a519-42ea-b514-135450b83b42)

