# COVID-19-Detection-using-Machine-Learning

---

## Introduction

The Coronavirus is increasing day by day all around the world. Not only the daily life of humans but also the economy of a country is deadly affected by SARS-CoV-2 also known as Covid-19. The medical scientist showed that Covid-19 patients suffer from lung problems. Both CT scans and X-rays are being used to diagnose coronavirus but due to low cost and time, a chest x-ray is more preferable to the other. To stop spreading the virus, quick identification of affected people is one of the top priorities. For identifying a covid patient at an early stage a deep learning-based method is proposed in this paper. A supervised learning-based algorithm with Convolutional Neural Network and ReLU activation function is used to identify Covid-19 virus from chest radiography (X-ray) images. A good amount of augmentation is done upon the dataset as the dataset is not that big which helps to generate a good prediction. The initial experiments show the model performs well on average but in covid cases, it shows exemplary results. I would like to emphasize that this approach is a pre-diagnostic step that would determine if a person needs to do the traditional test or not.

---

## Network Structure

The whole method’s structure can be dived into three parts: Dataset, Model and Evaluation Metrics. These three are the backbone of the whole project.

### Dataset
The dataset used in this model is collected from Kaggle, which contains a total of 6432 x-ray images that are subdivided into test and train datasets. This comparative big dataset provides various research paths about detecting the Covid-19 virus in various computer vision ways.
[Dataset Link](https://www.kaggle.com/prashant268/chest-xray-covid19-pneumonia)
  <img
  src="/images/data_table.jpg"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; align: center; margin: 0 auto; max-width: 100px">

### Model
The deep neural-based model contains different kinds of layers and functions such as a convolutional layer, fully connected layers, max-pooling and so on. A brief overview of these functions are given below, 
+ Convolutional Layer works as a filter that strides through the whole input image and generates a feature map. The height and weight of the filters are smaller than the input image.
+ Dense Layer or Fully connected layers are those neural layers where each neuron or node gets the input from all the neurons of the previous layer (flatten). Here, all the nodes are fully connected.
+ Max pooling is the way of taking the maximum value from the patch of the feature map where the max-pooling kernel is set.
+ Adam optimizer is an adaptive learning method. It computes individual learning rates for different parameters.
+ Early Stop Function: Early stop function is usually used to set a limit on the training of the model to prevent overfitting. It checks the validation loss in every epoch and compares the value with the previous validation loss. If the value is lower than the previous value the models continue to iterate but if the loss value is higher than the previous loss function in six consecutive terms it stops the model from further epoch.
+ Activation function:
  + 1.Rectified Linear Unit (ReLU) is used as the activation function for all the convolutional layers and the first two Dense layers in this model.
The purpose of the ReLU is to give non-linearity to the model. It set all the negative values to zero and preserves only positive values. This function helps to reduce unnecessary noises from the data. 
  + 2. Soft Max activation function is used for the last dense layer in this model. The function is used when the output value is needed to be normalized. It converts the inputs from weighted sum values into probabilities that range from zero to one.

### Evaluation Metric
