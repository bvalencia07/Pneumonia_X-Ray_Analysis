# Pneumonia_X-Ray_Analysis
![xray](https://github.com/user-attachments/assets/0d410063-3f9a-41b6-aa96-32d5c1e8d916)
## Overview
The following analysis takes a deeper dive into the research and understanding behind pneumonia. This sickness being an inflammatory condition of the lungs that fills the air sacks with pus and other liquids due to an infection caused by fungi, bacteria, or a virus. Pneumonia can lead to complications like respiratory failure, sepsis, and lung abscesses, especially in high-risk groups such as children, the elderly, and people with lung complications. With that in mind, early detection of pneumonia is crucial according to medical experts. This analysis does just that by taking a deeper look into various x-rays of children between ages of one and five, taken by Guangzhou Women and Children’s Medical Center and determining if the given x-ray image match to that of a person with pneumonia of not.
## Business Problem
With all this into consideration, our stakeholders, Guangzhou Women and Children’s Medical Center, are requesting for a model to be made that can be used to appropriately distinguish the difference between x-rays classified as "NORMAL" and "PNEUMONIA" in order to continue their efforts in combatting this sickness.
## Data Understanding
The data provided by the stakeholders, consists of 5,863 x-rays. All divided into two classes, patients with pneumonia and normal patients. This data is already slpit into three different groups/folders. The first group being for the training sample; 5,216 images. The second being for testing, with 624 images. And the last being for validation, consisting of only 16 x-ray images.
### Normal Patient
![Screenshot 2024-09-23 124613](https://github.com/user-attachments/assets/043d171f-0460-4302-a9a3-1aad4064a3c0)
### Patient with Pneumonia
![Screenshot 2024-09-23 124958](https://github.com/user-attachments/assets/3275e957-a3e4-4933-935e-c5dfdd54b769)
## Modeling
### Model 1: Baseline Model/ Densely Connected Neural Network
![Screenshot 2024-09-23 143215](https://github.com/user-attachments/assets/452fc4d2-0e7f-4d8e-90e2-5a97011c16e1)
![Screenshot 2024-09-23 143230](https://github.com/user-attachments/assets/8598d07d-694d-478d-9130-5715e98e1c6b)
The first model had a validation accuracy of 62 percent and a training accuracy of 87 percent. One can infer that this densely connected neural network has a poor performance due to the poor validation score; validation loss of 1.04. The training loss and validation loss have a large gap between thhem of approximately 0.76. Another sign of overfitting is that the curves diverge in different directions.
