# Brain Computer Interface 

![img](https://www.techslang.com/wp-content/uploads/2019/11/1111-e1573834183704.jpg)

## Table of Content:

 - [Introduction](#overview)
 - [The Proposed System](#bci)
 -  [Installation](#installation)
 - [File Descriptions](#files)
 - [Get Started](#get_start)
 - [Licensing  and Authors](#L&A)
  
<a name="overview"></a>
## Introduction

### 1.1 Project aim

To sum up, our project is aiming to provide a practical and low cost solution for the complications that might be found in the real world’s engineering diesel engine laboratories through providing a virtual model that is characterized by the reality of the diesel engine lab, ease of use using only VR headset and input gloves and also provides additional features that would help students achieve maximum output through immersion with the machine and visualize everything that’s happening inside it.


### 1.2 Project objectives

In order to achieve the project aim, we need to divide our project into three main objectives. First, we have to study the diesel engine lab in details and learn how to design a 3D simulation for the engine. After building the 3D model, the next step is to bring this model into a virtual world in which the student will be able to interact with our model. Now we have the VR world with our model inside. The next step is providing the hardware to be used to ensure the full immersion of the student with the virtual lab. We have decided to use human activity recognition input as a way of convincing the student’s mind? that everything around him is a reality rather than a virtual one to ensure full engagement. Finally, we need to work on the integration of all these parts to provide the best immersive learning experience.
### 1.3 The Brain Computer Interface 

Model evaluation is an essential phase in building engineering systems to ensure the quality and efficiency of the system. The proposed model is meant to replace the traditional mechanical labs that contain heave machines with a virtual-based technology that is assumed to be helpful in student’s understanding and interaction with machines. The challenge was how to evaluate the system so that student’s understanding can be indicated. After a lot of research, it’s found that a brain-computer interface (BCI) is the most suitable way to achieve that since it is widely used in applications similar to the one our team was working on.

BCI is a system that uses electrodes to establish direct communication between the brain and an external device such computer or robotic arm. There are two ways to establish a BCI system the invasive and non-invasive. The invasive requires a surgical operation to insert the electrodes under the patient’s skin. On the other hand, the non-invasive does not require that it is implemented by placing the electrodes on one’s scalp. Electroencephalography (EEG) is the most well-known technique in building a non-invasive BCI system that captures the brain's electrical activity. The simplicity of use, mobility, lower cost, and high temporal resolution are the main reasons for EEG popularity and what motivated the team to use it [36]. There are other alternatives, but they are not as efficient as the EEG.

BCI is used in many useful applications such as stress detection, motor imagery tasks, and spinal cord rehabilitation. A typical BCI is used to retrieve data from the brain and send them to an external device to perform a certain task. In the proposed system BCI using EEG is only used to extract the signals and classify them to get specific information.
<a name="bci"></a>
## The  Proposed System
### 2.1 Data collection 
The data collection experiment was designed based on the previous related work. On projects like the proposed one, subjects’ EEG data is collected from them when they are using the system. Thereafter, the data are labelled using a post-knowledge test. 

The experiment used consists of two phases. The first one is the subject using the proposed system while putting the EEG headset on. Then, to measure his/her knowledge and attitude, a knowledge and attitude questionnaire is used. The knowledge and attitude were chosen specifically to test how effective the proposed system is and the advantage it adds over the typical lab in terms of safety, concentration, and physical interaction with the machine. 

The questionnaire we used consisted of 10-likert questions. Each question has five choices, strongly disagree, disagree, neutral, agree, and strongly agree. The questions were designed to test student’s interest in the content through questions that measures his/her interaction during using the system. Moreover, there were some other questions that were knowledge based. After recording the EEG signal, student’s answers were analysed and based on the mean, the answers were used to label the EEG signals by dividing them into two classes. Class zero students who were not interest and class one those who were not interested. The results of the experiment are summarized below (Table 2-1):
To have a balanced interest level among participants, students from different engineering majors were selected. They were asked if they’re interested to participate in the experiment and those who showed interest were selected. When they arrived at the experiment place, they were informed of everything about the experiment, how they can use the system and control the engine, and they were asked to answer the post-knowledge and attitude 
questionnaire honestly with no guessing. After that, they signed up a consent that they agreed on volunteering in our experiment and using the collected data for research purposes. 

They started to use the system while putting the EEG headset on to record their brain activity using the neurosky one-channel sensor at a sampling frequency of 50 HZ. Finally, they answered the post-knowledge and attitude questionnaire. Participants’ demographics are summarized below (Table 2-2).

![table](https://github.com/sam1o1/Brain-Computer-Interface-To-Measure-Student-s-Interest/blob/main/Brain-Computer%20Interface/img/table2-1.jpg?raw=true)

### 2.2 Data preparation & exploration 
In the data preparation phase, the raw data was prepared to work with it in python. After importing the data of all participants, it was stored in one dictionary with keys that were named the same as each participant’s id. (figure 5-5) is an example of the first 8 rows of the record of channel Fp1 of  subject_01. Afterward, part of the data was visualized with the aim of exploring the data and picturing the effect of signal processing.

### 2.3 Signal processing        
The signal processing methods applied in the proposed system are the same as the authors in  used. The filters are defined using the Scipy package to remove artifacts. The filters used are third-order median filter, low pass filter, high pass filter, and notch filter. For denoising and smoothing, wavelet denoising, and a Savitzky–Golay filter were used. First, the raw signals were filtered using the third-order median filter to remove the background noise. then, the filtered signals were further filtered using low-pass and high-pass filters. A Butterworth filter with order 5 was used to design these filters at cutoff frequencies of 0.5 HZ and 50 HZ for the low and high filters respectively. The Butterworth filter is a signal processing filter with a frequency response in the passband that is as flat as possible. A maximally flat magnitude filter is another name for it. (figure 2-3) shows the designed bandpass filter using both the low pass and high pass filters. (figure 2-4) shows the result of applying the Butterworth filter on a sample of the data. 

![2-3](https://github.com/sam1o1/Brain-Computer-Interface-To-Measure-Student-s-Interest/blob/main/Brain-Computer%20Interface/img/2-3.jpg?raw=true)

![2-4](https://github.com/sam1o1/Brain-Computer-Interface-To-Measure-Student-s-Interest/blob/main/Brain-Computer%20Interface/img/2-4.jpg?raw=true)

Subsequently, a notch filter was applied to reject power interference at 60 HZ. Furthermore, the signals were denoised using a de-noising method based on multilevel wavelet decomposition. The number of wavelet levels was 5, the mother wavelet was Symlets. Lastly, the signals were smoothed using the Savitzky–Golay filter. Figure(2-5,6) presents the result of the signal processing techniques applied to the proposed system. 


![2-5](https://github.com/sam1o1/Brain-Computer-Interface-To-Measure-Student-s-Interest/blob/main/Brain-Computer%20Interface/img/2-5.jpg?raw=true)


![2-6](https://github.com/sam1o1/Brain-Computer-Interface-To-Measure-Student-s-Interest/blob/main/Brain-Computer%20Interface/img/2-6.jpg?raw=true)

### 2.4 Windowing 
After filtering the signals, the clean signals were segmented using a sliding window. The process involved some steps. First, a 4-second width window was used to loop through the time-domain signal dividing it into small segments for 4 seconds each. The window width was decided based on the literature done. To decide whether the sliding window has to be overlapping or non-overlapping, both methods were tried. The result was that the overlapping method was more efficient and resulted in higher accuracy. We started with a 50% overlap.

 Then, we tried different values until the highest accuracy was achieved at a 4-second sliding window and 3-second overlap. 
The segments after that were converted from the time-domain to the frequency-domain using the Fast Fourier transform. In addition to that, the signals were obtained in the time-frequency domain as stated in [36] the features extracted in the time-frequency domain result in getting a higher classification accuracy. The Wavelet transformation was used in converting the signals to the time-frequency domain. 
### 2.5 Feature Extraction 
The features extracted from each column in time, frequency, and time-frequency domains were:
The mean x̄ of a data set is the sum of all the data divided by the count n.

                       (Sum of terms)/(number of terms )

The standard deviation is a statistic that measures the amount of variation or dispersion in a set of numbers. A low standard deviation implies that the values are close to the set's mean, whereas a high standard deviation shows that the values are dispersed across a larger range.

                              σ= √∑(X_(i )-μ)/N
- σ	=	population standard deviation
- N	=	the size of the population
- X_(i )	=	each value from the population
- μ	=	the population mean

In statistics, the median absolute deviation is a robust measure of the variability of a univariate sample of quantitative data. It can also refer to the population parameter that is estimated by the MAD calculated from a sample.

                      median absolute deviation=|X_(i )-mean|

X_i	= each value

In descriptive statistics, the interquartile range, also called the midspread, middle 50%, or H‑spread, is a measure of statistical dispersion, being equal to the difference between 75th and 25th percentiles, or between upper and lower quartiles. In information theory, the entropy of a random variable is the average level of "information", "surprise", or "uncertainty" inherent in the variable's possible outcomes. In addition to the minimum and maximum value in each column. The entropy, energy, skewness, and kurtosis features that work well in classifying EEG data were also extracted from the data in the three domains. 

### 2.6 Classification 
Four machine learning classifiers were used to classify the EEG data the LinearDiscriminantAnalysis, support vector machines, random forest, and KNN. After getting split into training and test sets, the training data was fed into the classifiers and the test set was used to measure the classifier's accuracy. 

### 2.7  Results  
To Evaluate models’ performances, accuracy, sensitivity, and the F1 score were used. The results are divided into three categories the result without feature reduction and feature selection, with feature selection, and with feature selection and reduction. The results of each category were evaluated using the metrics above and the classification computational cost.


<a name="installation"></a>
## Installation
In order to run this project you need to install:
This project uses the following software and Python libraries:

-   [Python](https://www.python.org/downloads/release/python-364/)
- [MNE](https://mne.tools/stable/index.html)
- [glob](https://docs.python.org/3/library/glob.html)
-   [NumPy](http://www.numpy.org/)
-   [pandas](http://pandas.pydata.org/)
-   [scikit-learn](http://scikit-learn.org/0.17/install.html)  (v0.17)
-   [Matplotlib](http://matplotlib.org/)
- [skimage](https://scikit-image.org/)
- [pywt](https://pywave)

You will also need to have software installed to run and execute a  [Jupyter Notebook](http://ipython.org/notebook.html).

If you do not have Python installed yet, it is highly recommended that you install the  [Anaconda](http://continuum.io/downloads)  distribution of Python, which already has the above packages and more included.

<a name="files"></a>
## File Descriptions

 1.  `EEG_Dataset`: This folder contains the dataset and a readme file that describes the labeling process. 
  2. `Signal Processing`: The singal processing Jupyter notebook and the resulted clean data as `csv`
  3.    `Machine-learning`:  The ML Jupyter notebooks. 
 ## Get Started
 <a name="get_start"></a>
Use the following command to download the files : 

    git clone https://github.com/sam1o1/Brain-Computer-Interface-To-Measure-Student-s-Interest
<a name="L&A"></a>
## Licensing  and Authors
Author : Eslam Abdelghany
Email: eslam322_1@hotmail.com

 
 

