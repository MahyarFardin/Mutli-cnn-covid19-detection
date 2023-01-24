# Mutli-cnn-covid19-detection

This repository is a python regeneration of a [this paper](https://www.researchgate.net/publication/344146042_Computer-aided_detection_of_COVID-19_from_X-ray_images_using_multi-CNN_and_Bayesnet_classifier) which is a matlab implementation for computer aided covid 19 detection using multi-cnn and Bayesnet (Brnoulli classifier in my case) from X-ray images.

**Dataset**
The dataset used in this paper was gathered from [this open source repo](https://github.com/ieee8023/covid-chestxray-dataset.git) and [this kaggle page](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjfoPWMiOD8AhXbgv0HHXmIBSUQFnoECBsQAQ&url=https%3A%2F%2Fwww.kaggle.com%2Fdatasets%2Ftawsifurrahman%2Fcovid19-radiography-database&usg=AOvVaw0TJDpAmkHaiUEuDNkxfXnF).

I combined these two datasets and made a balanced dataset of 563 *covid19* and 563 *of other illnesses*, but due to lack of resource and time I only used 400 of images in each category.

**Preprocessing**

I converted all of the images to black and white and saved them in a seperated folder but
<hr/>

- Feature Extraction

We used 2 pre trained CNNs for feature extraction and extracted 1280 features from **MOBLENET** and 2048 features from **XCEPTION** and replaced each image with a 1x3328 matrix.

- Feature selection

First, in this step I used a correlation based feature selection. I used both correlation and pearson-r for removing most correlated features, but I could not since there was none.

Second, I used a forward stepwise feature selection which helped me select 15 most important features.

- Classification

I used many algorithms and even tried to tune them but the best performing classifier was bernoulli classifier which gave me a 86 percent accuracy.
