# Generative Data Augmentation

Github repository for the article below: 


Burak Aktas, Doga Deniz Ates, Okan Duzyel, and Abdurrahman Gumus "**Diffusion‑based data augmentation methodology for improved performance in ocular disease diagnosis using retinography images**", International Journal of Machine Learning and Cybernetics (2024) 

# Abstract 

Deep learning models, integral components of contemporary technological landscapes, exhibit enhanced learning capabilities with larger datasets. Traditional data augmentation techniques, while effective in generating new data, have limitations, especially in fields like ocular disease diagnosis. In response, alternative augmentation approaches, including the utilization of generative AI, have emerged. In our study, we employed a diffusion-based model (Stable Diffusion) to synthesize data by faithfully recreating crucial vascular structures in the retina, vital for detecting eye diseases by using the Ocular Disease Intelligent Recognition dataset. Our goal was to augment retinography images for ocular disease diagnosis using diffusion-based models, optimizing the outputs of the fine-tuned Stable Diffusion model, and ensuring the generated data closely resembles real-world scenarios. This strategic approach resulted in improved performance in classification models and augmentation outperformed traditional methods, exhibiting high precision rates ranging from 85% to 76.2% and recall values of 86%, and 75% for 5 classes. Beyond performance enhancement, we demonstrated that the inclusion of synthetic data, coupled with data reduction using the t-SNE method, effectively addressed dataset imbalance. As a result of synthetic data addition, notable increases of 3.4% in the precision metric and 12.8% in the recall metric were observed in the 7-class case. Strategically synthesizing data addressed underrepresented classes, creating a balanced dataset for comprehensive model learning. Surpassing performance improvements, this approach underscores synthetic data’s ability to overcome the limitations of traditional methods, particularly in sensitive medical domains like ocular disease diagnosis, ensuring accurate classification. 

# Repo Contents 
**classification_general_VGG19.ipynb:** Uses the VGG19 model for image classification.

**custom_csv_maker.ipynb:** Creates custom CSV files from dataset classes.

**different-csv-concatenation.ipynb:** Concatenates multiple CSV files for combined analysis or training.

**fine-tuning-stable-diffusion.ipynb:** Fine-tunes Stable Diffusion for generating improved outputs.

**photo_similarity_matcher.ipynb:** Matches photo similarities using image comparison techniques.

**synthetic-and-real-data-concate.ipynb:** Merges synthetic and real data for larger classification datasets.

**synthetic_data_classification.ipynb:** Classifies data using synthetic datasets.

**synthetic_data_classification_model_creation.ipynb:** Builds models for classifying synthetic data.

**traditional-data-augmentation.ipynb:** Applies basic data augmentation like flipping or scaling to increase dataset variability.


## Dependencies 

To install required dependencies, use the provided `requirements.txt` file. 

```bash
pip install -r requirements.txt
```

# Algorithm Flow 

Our research enhances deep learning-based ocular disease classification by generating realistic synthetic data with Stable Diffusion. The goal is to address limitations of traditional data augmentation by creating high-quality synthetic samples for underrepresented classes in the ODIR dataset. We show that integrating real and synthetic data improves classification accuracy and model performance. 

Our process consists of six steps as shown below to generate and evaluate synthetic data for ocular disease diagnosis. 

<!-- ![image](https://github.com/user-attachments/assets/cfbd6ad7-ee9f-4ee6-bdad-076a60d0234b) -->
<img src="https://github.com/user-attachments/assets/cfbd6ad7-ee9f-4ee6-bdad-076a60d0234b" alt="image" width="700">

## Step 1: Fine-tune the Diffusion-Based Data Augmentation Model: 
In the first step of our process, we fine-tuned the diffusion-based image generation model (Stable Diffusion) based on specific classes and instances that we wish to generate. In order to generate synthetic data that satisfies our desired criteria, this customized fine-tuning is essential.   

## Step 2: Generating a Synthetic Dataset: 
Following the model's fine-tuning, we employed a Stable Diffusion model to generate a substantial synthetic dataset. This dataset forms the basis for the creation of our synthetic data.  

## Step 3: Labeling the Synthetic Data: 
Upon the creation of the synthetic dataset, which consists of unlabeled data, it becomes necessary to assign labels to this data. To accomplish this, we constructed a disease classification model. In this model, we utilized a pre-trained VGG19. This model was fine-tuned using real data, and its classification accuracy became a benchmark for our subsequent steps (Figure 2).  

![image](https://github.com/user-attachments/assets/53cdd9e9-bdd0-4d23-b47d-3f05259261f1)

## Step 4: Data Reduction for Dominant Classes (Diabetes and Normal) using t-SNE: 
Image selection of dominant classes, namely diabetes and normal, was made using the t-SNE method referred to as “Selected Images”. 

![image](https://github.com/user-attachments/assets/280869e9-489d-4448-a4b1-23f0203ac3bb)

## Step 5: Integrating Synthetic Data, Real Data, and Selected Images: 
With the completion of the labeling process through the classification model, the synthetic data and selected images were integrated with our existing real data. This union resulted in the formation of new datasets. 

## Step 6: Evaluation and Testing for Different Cases: 
The final step involves subjecting the newly formed Hybrid datasets to a series of tests. We carefully assessed the impact of the synthetic data addition on accuracy. Once again, a pre-trained VGG19 model was utilized. This step allowed us to draw conclusions and provided insights into the effectiveness of our synthetic data augmentation in enhancing classification performance.

## Dataset 
Ocular Disease Intelligent Recognition (ODIR), used in this study, is publicly available at https://odir2019.grand-challenge.org/. 

https://www.kaggle.com/datasets/andrewmvd/ocular-disease-recognition-odir5k 

# Results and Discussions 

## Creating synthetic data using customed prompts 
Stable Diffusion was employed to overcome limitations of traditional augmentation methods in the Ocular Disease Intelligent Recognition (ODIR) dataset, which suffered from significant class imbalance. Five underrepresented classes were overshadowed by dominant ones like Diabetes and Normal. Synthetic data, generated using specific prompts, replicated complex retinal vascular structures to improve class representation and balance the dataset. Fine-tuning ensured that the synthetic data closely resembled real data, broadening the dataset without introducing artificial features. This approach significantly enhanced the model's diagnostic performance, particularly for underrepresented classes, as demonstrated in figure below.

<!-- ![image](https://github.com/user-attachments/assets/a2eb7d46-631e-4a63-8f40-4be6f3db596a) -->
<img src="https://github.com/user-attachments/assets/a2eb7d46-631e-4a63-8f40-4be6f3db596a" alt="image" width="600">

## Fine‑tuning and prompt engineering significantly influenced the quality of synthetic data
Fine-tuning and prompt engineering play a crucial role in improving the quality of synthetic data for ocular diseases such as Glaucoma, Hypertension, Cataract, AMD, and Pathological Myopia. Specific prompts enable more realistic representations, capturing detailed disease-specific features often missed or distorted with generic prompts. The study demonstrates that tailored prompt selection, combined with fine-tuning, is essential for generating high-quality, accurate synthetic data, as shown in figure below. 

<!-- ![image](https://github.com/user-attachments/assets/2bf66838-d54a-4a6d-b779-df169356afad) --> 
<img src="https://github.com/user-attachments/assets/2bf66838-d54a-4a6d-b779-df169356afad" alt="image" width="600">

## Demonstrating the positive impact of synthetic data on model performance 
Synthetic data augmentation was applied to address class imbalance by focusing on underrepresented classes while excluding dominant ones. Diffusion-based models generated synthetic data, leading to significant improvements in accuracy, F1-Score, precision, and recall, as detailed in Table and Figure below. The accuracy and loss graphs demonstrated faster convergence and higher performance, confirming the effectiveness of synthetic data in enhancing model performance. 

**Table:** 5 class classification results with synthetic data augmentation. Scenario 1 (sc1): real data, Scenario 2 (sc2): real data + x2 synthetic data.
<!-- ![image](https://github.com/user-attachments/assets/84dec8ec-61d0-4217-bacf-bd328615ba8d) --> 
<img src="https://github.com/user-attachments/assets/84dec8ec-61d0-4217-bacf-bd328615ba8d" alt="image" width="600">


## Impact of diffusion‑based data augmentation on model performance versus traditional methods 
Stable Diffusion-based data augmentation outperformed traditional methods by producing augmented data closely aligned with the underlying data distribution. Unlike conventional approaches, which often distort or over-process data, diffusion-based techniques preserved critical features, enabling better generalization and improved accuracy. Focusing on 5-class scenarios highlighted the saturation point of augmentation benefits, demonstrating that diffusion-based methods excel in handling the complexities of ocular disease images. As detailed in Table below, this approach significantly enhanced model performance compared to traditional augmentation methods. 

**Table:** 5 class classification comparison between traditional and synthetic data augmentation results for different scenarios. sc1: real data, sc2: real data + x1 synthetic data augmentation, sc3: real data + x1 traditional data augmentation, sc4: real data + x2 synthetic data augmentation, sc5: real data + x2 traditional data augmentation.

<!-- ![image](https://github.com/user-attachments/assets/7a36055d-8bee-43e2-925e-1f64f56cd8b9) -->
<img src="https://github.com/user-attachments/assets/7a36055d-8bee-43e2-925e-1f64f56cd8b9" alt="image" width="500">

## Analyzing the limitations of synthetic data augmentation: the saturation point and its impact on model accuracy 
Synthetic data improves model performance by increasing diversity and aiding generalization, but its benefits diminish beyond a saturation point. Excessive synthetic data can deviate from real-world representations, leading to overfitting and reduced generalization to new data. This phenomenon, akin to photocopying, introduces distortions that overshadow real data's characteristics, reducing model effectiveness. An ablation study, summarized in Table below, identified the optimal balance between real and synthetic data. Doubling the synthetic data (case ‘sc5’) yielded the best results, while adding more synthetic data beyond this point led to performance decline. 

**Table:** 5 class classification results with synthetic data augmentation for different scenarios. sc1: real data, sc2: real data + x0.5 synthetic data, sc3: real data + x1 synthetic data, sc4: real data + x1.5 synthetic data, sc5: real data + x2 synthetic data, sc6: real data + x4 synthetic data. 

<!-- ![image](https://github.com/user-attachments/assets/122ddbac-09d8-4448-af34-5d383ec2f3d6) -->
<img src="https://github.com/user-attachments/assets/122ddbac-09d8-4448-af34-5d383ec2f3d6" alt="image" width="600">

# Conclusions 
This article has showcased the innovative impact of generative AI, particularly diffusion-based models, in the realm of synthetic data generation. In our research, the Stable Diffusion model was applied to the Ocular Disease Intelligent Recognition (ODIR) dataset, a rich source of ocular health data but highly imbalanced. By fine-tuning and conducting rigorous experiments, we successfully combined synthetic data with real data to mitigate class imbalance and improve data representation for dominant classes. In essence, the objective is to improve diagnostic accuracy in sensitive medical fields, such as ocular disease detection, through advanced synthetic data generation techniques. Our analysis involved a thorough comparison between traditional data augmentation techniques and the output from the Stable Diffusion model. In this comparison, diffusion-based data augmentation showed promising results. It achieved precision rates ranging from 76.2\% to 85\% and recall values between 75\% and 86\%, indicating a noteworthy improvement over traditional augmentation methods. The results were notable: the diffusion model consistently showed improved the classification performance over traditional methods, highlighting its capacity to enhance machine-learning model accuracy through advanced data generation. This observation suggests the potential usefulness of diffusion-based models in data augmentation and model performance optimization. The study's results indicate that integrating synthetic data, particularly that generated by diffusion models, can significantly improve classification model performance. After synthetic data addition, notable increases of 3.4\% in the precision metric and 12.8\% in the recall metric were observed in the 7-class case. This strategy is particularly promising for boosting accuracy and robustness in machine-learning models across various medical fields, including dermatology, pathology, and radiology. Given the rapid advancements in Latent Diffusion-Based Models, further exploration into their applications in data augmentation and classification tasks is both necessary and promising. Our study not only confirms the effectiveness of these models in tackling data scarcity but also paves the way for future research in using synthetic data to enhance healthcare diagnostics and more.  



# Citation 

If you use the our research in your studies, please cite our related publication: 

```bibtex
@article{aktas2024diffusion,
  title={Diffusion-based data augmentation methodology for improved performance in ocular disease diagnosis using retinography images},
  author={Aktas, Burak and Ates, Doga Deniz and Duzyel, Okan and Gumus, Abdurrahman},
  journal={International Journal of Machine Learning and Cybernetics},
  pages={1--22},
  year={2024},
  publisher={Springer}
}

