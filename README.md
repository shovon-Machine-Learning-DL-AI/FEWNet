# FEWNet
This repository serves as the source code for the research paper titled "Forecasting CPI Inflation under Economic Policy and Geo-political Uncertainties". The paper introduces a new approach called the **Filtered Ensemble Wavelet Neural Network (FEWNet)**, which is capable of generating accurate long-term predictions for CPI inflation. The idea utilizes a maximum overlapping discrete wavelet transform on the CPI inflation data to extract high-frequency and low-frequency signals. The wavelet-transformed series and filtered exogenous variables are fed into autoregressive neural networks downstream to get the ultimate ensemble forecast. Our theoretical analysis demonstrates that FEWNet effectively minimizes the empirical risk in comparison to individual, fully connected neural networks. Furthermore, we provide evidence that the real-time forecasts generated by the suggested algorithm, using a rolling-window approach, are notably superior in accuracy compared to standard forecasting methods used for comparison. In addition, we utilize conformal prediction intervals to measure the level of uncertainty linked to the projections produced by the suggested method. The outstanding performance of FEWNet can be ascribed to its ability to efficiently capture non-linearities and long-range relationships in the data via its flexible architecture.

* FEWNet integrates the maximum overlapping discrete wavelet transformation (MODWT) approach, economic filtering methods including the Hodrick-Prescott (HP) filter and Christiano-Fitzgerald (CF) filter, and the autoregressive neural network with exogenous variables (ARNNx).

* The code module #[economic filters](/code/data_analysis/economic_filters.py) consists of the generic code to derive the trend and cycle components using HP and CF economic filters.

* The global characteristics of the CPI Inflation, EPU, and GPRC can be derived using #[global_characteristics](/code/data_analysis/Global_characteristics.R) code module. This R code module calculates key statistical properties like skewness, kurtosis, long-range dependency, seasonality, stationarity, and non-linearity of the above-mentioned time series.

* The application of Wavelet Coherence Analysis (WCA) for analyzing the spatio-temporal association among variables is available in # [WCA](/code/Wavelet_Coherence_Analysis/WCA_BRIC.R). The WCA methodology offers a valuable method for examining the interconnection and simultaneous movement of two non-stationary signals in the time-frequency domain.
  
* The overall architectural design of the algorithm for generating long-term forecasts is shared below:
![architecture_FEWNet](https://github.com/shovon-Machine-Learning-DL-AI/FEWNet/blob/main/architecture_FEWNet.jpg)

* The following image illustrates the key steps for generating the forecasts using the FEWNet algorithm:
![Pseudo_Code_FEWNet](https://github.com/shovon-Machine-Learning-DL-AI/FEWNet/blob/main/PseudoCode_FEWNet.jpg)

* This repository contains the datasets for the CPI Inflation numbers along with the EPU and GPRC indices for the BRIC countries, and these datasets have been used in the downstream model development exercise. In order to access the dataset, please refer to the #[dataset](link to the dataset) section in GitHub. For more details about the datasets, please refer to the paper #[paper](ArXiv link). In our study, we consider the monthly CPI numbers for BRIC countries from 2003-01 to 2021-11 released by FRED (Federal Reserve Bank of St. Louis)[FRED - BRAZIL CPI](https://fred.stlouisfed.org/series/BRACPIALLMINMEI). 

* The source code for the proposed FEWNet model can be accessed through #[FEWNet](/code/FEWNet/FEWNet_BRIC_12M_24M_with_ConformalPI_calc_V2.R). The proposed framework consists of two hyper-parameters $(p,k)$, where $p$ denotes the number of lagged input observations and $k$ indicates the number of nodes in the hidden layer of the proposed EWNet model. The hyper-parameter $p$ is tuned by minimizing the Symmetric Mean Absolute Percentage Error (SMAPE) metric on the validation set. The optimized values of these hyper-parameters for different economies are highlighted in the paper and can be accessed through the source code for the FEWNet. Moreover, we also share a **framework for Grid-search CV** to determine the optimal values of the hyper-parameters (HPs) at the end of the source code. Interested users can experiment with the code for different ranges of values for the HPs or for other data types.

* The source code #[FEWNet](/FEWNet/FEWNet_BRIC_12M_24M_with_ConformalPI_calc_V2.R) also contains a code module to derive the **conformalised prediction intervals (CPI)** for the forecasts generated by the FEWNet Model. Similarly, for other models, the CPIs can be calculated using the same code module.
  

