#  Abstract:

# Team Name: 
glitchinthe

# Team Members:         
1. Nimish Santosh
2. Kandavel Arul
3. Mohan Pierce

# Selected Theme: 
Monitoring Hotspots in Distributed Computing.


# Problem Statement:
Now a days, most online services hosted in data centre servers demand uninterrupted 24x7 services. A hotspot is an overloaded condition of the physical machine (PM) where it does not have adequate resources to serve immediate demanded request. Hotspots are unfavourable situations which cause SLA violations in some scenarios. We learnt that hotspots in data centers are caused due to a lack of resources to satisfy the peak immediate requests from clients. The nature of resource utilization in data centers are totally dynamic in context and may lead to hotspots. During the occurrence of the hotspot, the downtime of physical servers increases drastically which degrade the performance level of PM and may lead to SLA violation. Frequent creation of hotspots in physical servers affect qoS of entire system. It is because additional cooling systems has to be provided to cool the overloaded machines. So, handling hotspots are very essential especially when the data centre is handling high available or online services. 


# Description of desired application:
Here we propose to use a Trend Aware Regression (TAR) method as a load prediction model and perform linear regression analysis to predict the formation of hotspots. If the resource utilization shows a consistent increase for some time window, then there is a high probability of a hotspot in the near future. Due to the unpredictable nature of resource requirements in data-centres, it difficult to find out a systematic pattern in the usage of resources. This affects the accuracy of prediction models and so the more common models for time-series regression like AR, LR, ARIMA, EWMA (Exponential Weighted Moving Average) are not fit into all scenarios.


# Solution and Methodology:

# How we intend to solve the problem:
Autonomated management of cloud workloads of any kind requires effective response to spikes and huge requirements in short span of time. Therefore we plan to use Trend Aware Regression (TAR) method as a load prediction model and perform linear regression analysis to predict the formation of hotspots in the physical servers of data centers. The challenging and contradictory features of data-centre workloads like large variability, poorly autocorrelated, non-linear and heavily tailed distribution make it more difficult to model them mathematically and any single function could not include all these characteristics with required significance. We plan to use the CPU usage, memory usage and network-bandwidth usage in the servers as independent variables to predict the formation of hotspots. We conducted significant research and discovered that the entire utilization of resources in any physical machine can be characterized by the above three variables. As mentioned before, existing methods like LR, AR, ARIMA and EWMA give inaccurate predictions due to the above difficulties, however a recent paper has outlined that in similar situations, TAR has worked significantly better and has consistently given more accurate predictions.

In the TAR method, the degree of variation between the current points in the prediction window is used to forecast the future points. The TAR model can provide accurate results in its predictions. We aim to provide an alarm period for the cloud administrators to provide enough resources to avoid hotspot situations well in advance by a prediction window t. We plan to use precision error to evaluate the model's performance where the error is characterized by the difference between predicted value and the true value which occurs after prediction window t. A predicted state will be considered as a potential hotspot only if the values for all the three independent variables are above a particular threshold. Due to the inherent nature of TAR's accurate predictions in similar use-cases, we hope to achieve high reliablility in predicting future hotspots.


# Constraints:
- We require data along with situations indicating hotspots as a reference to train the model.
- Post deployment we would require a dedicated system to monnitor the resources of other systems 24x7 to predict hotspots.


# Tech stack: 
1. PyTorch - For constructing the model itself.
2. Fastai - A wrapper over pytorch, to be used in later stages for optimizing and bumping up the accuracy.

The reasons for choosing the above libraries to solve the problem are simple. PyTorch makes it easy to construct any kind of model by giving us all the basic building blocks needed. Moreover, it is extremely simple to debug. Fastai gives access to various classes and methods built over PyTorch to assist in every step of the process but comes in handy especially to find the ideal hyperparameters in order to obtain the best model possible.