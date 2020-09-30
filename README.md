# Covid-19-Detection
Detecting Covid-19 from X-ray Images.

<img src="https://github.com/manthanpatel98/Covid-19-Detection/blob/master/images/covidimg.jpg" height="400">

---

## **Covid-19 Detection Project**

<img src="https://github.com/manthanpatel98/Covid-19-Detection/blob/master/images/Covid.gif" width="600">

### [**WebApp**](https://covidxraydetection.herokuapp.com/)

---

## Motivation:
To build a CNN model for detecting COVID-19 and create a complete end to end Project.

---

## X-ray Dataset:
* Dataset of X-ray Images are taken from [Kaggle](https://www.kaggle.com/praveengovi/coronahack-chest-xraydataset).
* Check Chest_xray_Corona_Metadata.csv and Chest_xray_Corona_dataset_Summary.csv from the given link for COVID-19 infected X-ray images. 
---

## Picking Images:
* Here, I have manually chosen images of Covid-19 and Normal State.
* Entire model is trained on total around 400 images.
* For testing, I have used around 50 images.

---

## Model:
* Below is the model that I have created.
<img src="https://github.com/manthanpatel98/Covid-19-Detection/blob/master/images/covid.h5.png" height="700">

* If you also want to visualize your model check [Netron](https://lutzroeder.github.io/netron/).

### Understanding the Model:

#### **Input Image:**
* Here, the input image is (224,224,3) which means image is (224,224) size with RGB color.

#### **Layers:**
* **Conv2D Layer(3,3,3,32):** Conv2D Layer contains 32 kernels, size (3,3) **====>** Output: 32 images of size (222,222).
* **Conv2D Layer(3,3,32,64):** Conv2D Layer contain 64 kernels, size (3,3) **====>** Output: 64 images of size (220,220).
* **MaxPool2D Layer (3,3):**  MaxPool2D Layer is applied with (3,3) pool-size **====>** Output: 64 images of size (73,73).
* **Dropout Layer**
* **Conv2D Layer(3,3,64,64):** Conv2D Layer contain 64 kernels, size (3,3) **====>** Output: 64 images of size (71,71).
* **MaxPool2D Layer (3,3):**  MaxPool2D Layer is applied with (3,3) pool-size **====>** Output: 64 images of size (23,23).
* **Dropout Layer**
* **Conv2D Layer(3,3,64,128):** Conv2D Layer contain 128 kernels, size (3,3) **====>** Output: 128 images of size (21,21).
* **MaxPool2D Layer (3,3):**  MaxPool2D Layer is applied with (3,3) pool-size **====>** Output: 128 images of size (7,7).
* **Dropout Layer**
* **Flatten Layer**: This will flatten all the (7,7,128) images **====>** Output: (6272).
* **Dense Layer(6272,128):** Here Flattened array will be passed to 128 neurons in the Hidden Layer with applying 'relu' Activation Function **====>** Output: (128).
* **Dense Layer(128,2):** Output of 128 Neurons is passed to 2 Neurons with Activation Function 'softmax' which will help in deciding final output. **====>** Output: (2).

* Here, The **Images are converted into different dimensions according to applied different Mathematical Equations** based on Conv2D layer, MaxPolling and Padding.

---

## **Loss & Accuracy:**

<img src="https://github.com/manthanpatel98/Covid-19-Detection/blob/master/images/acc-val.png" height="250">

### **Accuracy:**
<img src="https://github.com/manthanpatel98/Covid-19-Detection/blob/master/images/acc.png" height="250">

### **Loss:**
<img src="https://github.com/manthanpatel98/Covid-19-Detection/blob/master/images/loss.png" height="250">

---

* Detail code about training model is available in [**Covid(GoogleColab).ipynb**](https://github.com/manthanpatel98/Covid-19-Detection/blob/master/Covid(GoogleColab).ipynb) and prediction based code is available in [**Covid.ipynb**](https://github.com/manthanpatel98/Covid-19-Detection/blob/master/Covid.ipynb).

* Check [**app.py**](https://github.com/manthanpatel98/Covid-19-Detection/blob/master/app.py) regarding WebApp code.

* Our Final Trained model is [**covid.h5**](https://github.com/manthanpatel98/Covid-19-Detection/blob/master/covid.h5).


