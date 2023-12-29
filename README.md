# FEWNet
This repository serves as the source code for the research paper titled "Forecasting CPI Inflation under Economic Policy and Geo-political Uncertainties". The paper introduces a new approach called the **Filtered Ensemble Wavelet Neural Network (FEWNet)**, which is capable of generating accurate long-term predictions for CPI inflation. The idea utilizes a maximum overlapping discrete wavelet transform on the CPI inflation data to extract high-frequency and low-frequency signals. The wavelet-transformed series and filtered exogenous variables are fed into autoregressive neural networks downstream to get the ultimate ensemble forecast. Our theoretical analysis demonstrates that FEWNet effectively minimizes the empirical risk in comparison to individual, fully connected neural networks. Furthermore, we provide evidence that the real-time forecasts generated by the suggested algorithm, using a rolling-window approach, are notably superior in accuracy compared to standard forecasting methods used for comparison. In addition, we utilize conformal prediction intervals to measure the level of uncertainty linked to the projections produced by the suggested method. The outstanding performance of FEWNet can be ascribed to its ability to efficiently capture non-linearities and long-range relationships in the data via its flexible architecture.

* FEWNet integrates the maximum overlapping discrete wavelet transformation (MODWT) approach, economic filtering methods including the Hodrick-Prescott (HP) filter and Christiano-Fitzgerald (CF) filter, and the autoregressive neural network with exogenous variables (ARNNx).
  
* The overall architectural design of the algorithm for generating long-term forecasts is shared below:
![architecture_FEWNet](https://github.com/shovon-Machine-Learning-DL-AI/FEWNet/blob/main/architecture_FEWNet.jpg)

* The following image illustrates the key steps for generating the forecasts using FEWNet algorithm:
![Pseudo_Code_FEWNet](https://github.com/shovon-Machine-Learning-DL-AI/FEWNet/blob/main/PseudoCode_FEWNet.jpg)

* This repository contains the datasets for the CPI Inflation numbers along with the EPU and GPRC indices for the BRIC countries, and these datasets have been used in the downstream model development exercise. In order to access the dataset, please refer to the [dataset](link to the dataset) section in the GitHub. For more detail about the datasets, please refer to the paper[paper](ArXiv link). In our study, we consider the monthly CPI numbers for BRIC countries from 2003-01 to 2021-11 released by FRED (Federal Reserve Bank of St. Louis)[FRED - BRAZIL CPI](https://fred.stlouisfed.org/series/BRACPIALLMINMEI). 

* 
  

