# LSTM-and-1D-CNN-based-Machine-Tools-Wear-Detection


# 1. Requirements:
    Desc. Python Libraries
  - Keras
  - Tensorflow
  - NumPy
  - Pandas
  - matplotlib
  - seaborn
  - scikit learn (sklearn)

# 2. Project Overview
-- Motor current data collected from the three axes of the vertical milling machine as shown in following figure:
<img width="591" alt="image" src="https://user-images.githubusercontent.com/125495015/219382921-5d27dc12-8633-46ca-b4c2-b82ae73b24b7.png">

-- Overview of the three approach with variuos Deep learning models 
<img width="1177" alt="image" src="https://user-images.githubusercontent.com/125495015/219341064-95b283de-06bb-4c83-9ffc-0a9c538e7edc.png">

# 3. Data Processing:
## From RAW data (json) to CSV data

## Data Cleaning
-- Spikes are removed.

<img width="838" alt="spikes_in_data" src="https://user-images.githubusercontent.com/125495015/219395461-b1694799-22fa-40c6-a0f3-732df94c7738.png">

-- After cleaning the spikes, it is observed that the part of the data is not in harmonic.
such as 1st, 13th and 25th milling cycle, in the figure. The data when the tool being used first time is also removed.
<img width="720" alt="milling_cycle" src="https://user-images.githubusercontent.com/125495015/219395821-15be6bee-2cf6-41a0-99eb-562f2f233d41.png">

<img width="719" alt="balanced_data" src="https://user-images.githubusercontent.com/125495015/219395871-2b518544-691b-47b2-b97d-c05438ba96b0.png">

## Final data-frame (balanced_data.csv)
<img width="541" alt="number of sequences" src="https://user-images.githubusercontent.com/125495015/219396093-1d626872-cc69-428d-9e62-19ca45c8a9f5.png">

# 4. Approach- a, b, c
![image](https://user-images.githubusercontent.com/125495015/219417761-81c79dee-d891-4cf7-a71a-5c680ba6f91b.png)

# 4. Approach- a, b, c
## Approach-a (1dCNN, LSTM, 1dCNN+LSTM)
### 1d CNN
<img width="739" alt="1dCNN_structure" src="https://user-images.githubusercontent.com/125495015/219408996-c2a203e5-cd31-4bce-bf5d-8b6d5b63cf6c.png">
<img width="793" alt="1dCNN_loss_accu" src="https://user-images.githubusercontent.com/125495015/219414662-ca50579d-b27c-4947-bc66-7169c8b0af6b.png">

### LSTM
<img width="641" alt="LSTM_structure" src="https://user-images.githubusercontent.com/125495015/219413582-7d341675-d441-4bd8-992c-8e1b1ce62db9.png">
<img width="790" alt="loss_accu_LSTM" src="https://user-images.githubusercontent.com/125495015/219414153-8ebdee68-ec43-4937-9915-279ff80e8d7d.png">


### 1dCNN+LSTM
<img width="739" alt="structure_1dCNN_LSTM" src="https://user-images.githubusercontent.com/125495015/219409600-e02a8d8d-8a37-4c13-a851-2a8a5b316642.png">
<img width="1010" alt="loss_accu" src="https://user-images.githubusercontent.com/125495015/219415518-ec2e3aa6-b06d-470a-9a2e-fd2a2b604bda.png">

## Approach-b (LSTM Autoencoder)
-- autoencoder_overview.

<img width="744" alt="autoencoder_overview" src="https://user-images.githubusercontent.com/125495015/219410303-22e55d0b-ae5d-4c0c-8d4d-f86fca2bde46.png">

-- selecting the threshold values
<img width="1074" alt="MAE_for_threshold" src="https://user-images.githubusercontent.com/125495015/219411588-853178f4-aef7-4a7e-9713-b8c0089a5bfa.png">

### LSTM_AE
<img width="590" alt="LSTM_AE_structure" src="https://user-images.githubusercontent.com/125495015/219409266-4544dc76-b441-4692-9d05-3589a00788ec.png">
<img width="995" alt="loss_accu_LSTM_AE" src="https://user-images.githubusercontent.com/125495015/219415877-54e1ec52-4cd3-4d19-b730-47c1ee040947.png">

###
<img width="973" alt="Confusion_matrix_approach_a_b" src="https://user-images.githubusercontent.com/125495015/219416907-dd562a69-b584-4a09-ad2b-7d2e450be0b9.png">

## Approach-c (Transfer Learning)
<img width="749" alt="transfer_learning_overview" src="https://user-images.githubusercontent.com/125495015/219411853-df44fe1e-dd23-4c08-ac74-90f2dee3aed7.png">

### Base_model
<img width="737" alt="loss_accu_base_model" src="https://user-images.githubusercontent.com/125495015/219412719-dcc371ec-0d46-40b3-b6b3-35603aa3e646.png">
<img width="760" alt="confusion_matrix" src="https://user-images.githubusercontent.com/125495015/219418324-8b123c96-8e87-4584-bb83-264301b9891b.png">

### Target_model
<img width="727" alt="loss_accuracy_before_after_TL" src="https://user-images.githubusercontent.com/125495015/219412495-7c6f2d82-f2b3-491c-a72f-4c49ee8a1cdd.png">
<img width="683" alt="Screenshot 2023-02-16 at 16 57 50" src="https://user-images.githubusercontent.com/125495015/219419672-530ec7af-108a-41b1-9376-774aae2e224e.png">
## Related Publication

This project is accompanied by the following published article:

(https://link.springer.com/article/10.1007/s00170-025-15069-x)

Demetgul, M., Darji, A. R., Tansel, I. N., Puchta, A., Fleischer, J., & Stork, W. (2025). Sensorless Tool Wear Estimation by using the Artificial Intelligence (AI) tools from the currents of motors generating linear motions. The International Journal of Advanced Manufacturing Technology, 1-19.

## Contributors

- Dr.Mustafa Demetgül – Academic Supervisor
- Apurv Rajeshkumar Darji – Developer



