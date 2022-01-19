
# Technical Task for Working Student Applicants

This project is a part of application for a Working Student position at Nyris GmbH.

This projects contains 4 Tasks : 

Task 1: Create a GitHub Repository
    
    This was successfully completed.

Task 2: Prepare Data

Google Colab Link : https://colab.research.google.com/drive/1l-YeDj0VjQ65naiheemwzyp3-uijW9QB?usp=sharing

    1. In the official website, follow the Download section to grab a copy of this dataset.
    Download only the following: 
        ● All Images and Annotations (this zip file contains images and annotations) 
        ● README (this text file describes the contents of above zip file in detail) 
    2. Run an Exploratory Data Analysis (EDA) on the downloaded dataset to get a better overview on the and skim through a few samples. 
    3. Now, split the data into training and testing subsets. 
        Follow the data splitting strategy described in Section 7.1 of the paper Deep Metric Learning via Lifted Structured Feature Embedding.


    Solution : 
    1. The dataset was downloaded, zipped and uploaded on Google Drive
    2. Drive was mounted and Dataset was split according to the paper referenced in the task.
    3. As a part of EDA, random images were plotted, class distribution was shown and other details of images such as type and shape were explored.



Task 3: Extract Embeddings

Google Colab Link : https://colab.research.google.com/drive/1T83C6ItlUyhtGj8iNCFdqWk9HXSl7ikl?usp=sharing

    Now follow the below steps to extract embeddings from the train and test data prepared in Task 2. 
    1. Pick a pre-trained CNN which is readily available from PyTorch or TensorFlow. 
    2. Extract train and test data features from the chosen pre-trained model. 
    3. Save the extracted features as a numpy file which will be required solving Task 4.

    Solution : 
    1. VGG16 was loaded without classification layers
    2. More layers were added and the model was trained on train data
    3. Model and its weights were saved.
    4. Feature Vectors for train and test dataset were generated.
    

Task 4: Evaluate

Google Colab Link : https://colab.research.google.com/drive/1l10gG065sdCoY_nrQwz61FRV8OyrAwUj?usp=sharing

    Steps for solving Task 4: 
    1. List a set of metrics that can be used to evaluate Image Retrieval models. 
    2. Describe what information each of the listed metrics will convey. 
    3. Describe how the training and test features (extracted in Task 3) will be used to compute evaluation metrics. 
    4. Finally, compute the listed evaluation metrics.

    Solution : 
    1. As per my research there are various metrics which could be used for evaluation of Image Retrieval task.
        > Recall
        > Recall@k
        > Precision
    
    2.  > Recall : Recall is the number of correct results divided by the number of results that should have been returned.
        > Recall@k : Number of test images with at least one similar returned image of same class by total number n of test images
        > Precision : Precision is the number of correct results divided by the number of all returned results.
    
    3. The Feature Vector of a test image is compared(using Cosine Similarity) with all the feature vectors present in the test data feature vectors. 
       The images with most similar feature vector are shown as a result. I have taken Recall@k as the choice of metric. 
       I have retieved top 5 images and this value is the value of k.

    4. Recall@k was chosen for this project with 200 test images(I could not use all the test images as it led to system hanging)

        For 200 test images recall value was 0.945

        This could be extrapolated to more images and I expect the recall would decrease.


