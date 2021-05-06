## MURA dataset : Musculoskeletal Radiographs Abnormality Detection
**Dataset Description:** (Dataset can be downloaded from here: https://www.kaggle.com/cjinny/mura-v11
- MURA is a large dataset of bone X-Rays containing 14,863 musculoskeletal studies of the upper extremity. 
- Each study contains one or more views (images) and is labeled as either normal or abnormal.
- Our dataset, MURA, contains 9,045 normal and 5,818 abnormal musculoskeletal radiographic studies of the upper extremity including the shoulder, humerus, elbow, forearm, wrist, hand, and finger.
- The training dataset consists of 14,863 studies(9045 normal, 5818 abnormal) whereas the validation dataset contains 207 studies. Total number of images is 40,561.
- Exploratory Data Analysis is in folder 'EDA'.

**Task Description:**
- MURA abnormality detection task is a binary classification task, where the input is an upper extremity radiograph and the expected output is a binary label y ∈ {0, 1} indicating whether the radiograph is normal or abnormal, respectively.

**Models implemented:** I have implemented two models: InceptionV2 model and Xception model using Tensorflow.
   
**Important points for both models:**
- Before feeding the images to the network, each image is normalized to have same mean and standard deviation as 0 and 1 respectively, scaled to 224 x 224 and augmented using following hyperparameters:
            <br>    - rotation_range = 30
            <br>    - brightness_range = [0.8,1.2]
            <br>    - horizontal_flip = True
- Used Adam optimizer with learning_rate = 0.0001 and default values of betas.
- Used binary_crossentropy loss function. 
- Used dropout regularisation of rate = 0.3 for inceptionV2 model.
- Used l2 regularisation of lambda = 1e-6 for Xception model
- Number of epochs ran for :-  Xception model : 35    and   inceptionV2 model : 80

**Results:**  Performance of both the models are compared with baseline model, DenseNet169 by P. Rajpurkar et al.(https://arxiv.org/pdf/1712.06957.pdf)
<table>
    <th>  </th>
    <th>Xception</th>
    <th>InceptionV3</th>
    <th>DenseNet169(baseline)</th>
    <tr>
         <td>prediction error</td>
         <td>0.195</td>
         <td>0.174</td>
       <td>0.153</td>
    </tr>
    <tr>
         <td>Cohen kappa score</td>
         <td>0.604</td>
         <td>0.652</td>
       <td>0.657</td>
    </tr>
    <tr>
         <td>f1_score</td>
         <td>0.80</td>
         <td>0.82</td>
       <td>0.84</td>
    </tr>
    <tr>
         <td>validation_accuracy</td>
         <td>0.796</td>
         <td>0.826</td>
       <td>0.838</td>
    </tr>
    <tr>
         <td>validation_loss</td>
         <td>0.493</td>
         <td>0.412</td>
       <td>0.389</td>
    </tr>    
  
  
