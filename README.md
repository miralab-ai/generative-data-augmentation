# generative-data-augmentation

Github repository for the article below: 


Burak Aktas, Doga Deniz Ates, Okan Duzyel, and Abdurrahman Gumus "**Data Augmentation Using Diffusion-Based Models for Improved Performance in Ocular Disease Diagnosis Using Retinography Images**", International Journal of Machine Learning and Cybernetics (2024) 

## Abstract 

Deep learning models, integral components of contemporary technological landscapes, exhibit enhanced learning capabilities with larger datasets. Traditional data augmentation techniques, while effective in generating new data, have limitations, especially in fields like ocular disease diagnosis. In response, alternative augmentation approaches, including the utilization of generative AI, have emerged. In our study, we employed a diffusion-based model (Stable Diffusion) to synthesize data by faithfully recreating crucial vascular structures in the retina, vital for detecting eye diseases by using the Ocular Disease Intelligent Recognition dataset. Our goal was to augment retinography images for ocular disease diagnosis using diffusion-based models, optimizing the outputs of the fine-tuned Stable Diffusion model, and ensuring the generated data closely resembles real-world scenarios. This strategic approach resulted in improved performance in classification models and augmentation outperformed traditional methods, exhibiting high precision rates ranging from 85% to 76.2% and recall values of 86%, and 75% for 5 classes. Beyond performance enhancement, we demonstrated that the inclusion of synthetic data, coupled with data reduction using the t-SNE method, effectively addressed dataset imbalance. As a result of synthetic data addition, notable increases of 3.4% in the precision metric and 12.8% in the recall metric were observed in the 7-class case. Strategically synthesizing data addressed underrepresented classes, creating a balanced dataset for comprehensive model learning. Surpassing performance improvements, this approach underscores synthetic data’s ability to overcome the limitations of traditional methods, particularly in sensitive medical domains like ocular disease diagnosis, ensuring accurate classification. 

## Repo Contents 

### Dependencies 


## Introduction 

Our research enhances deep learning-based ocular disease classification by generating realistic synthetic data with Stable Diffusion. The goal is to address limitations of traditional data augmentation by creating high-quality synthetic samples for underrepresented classes in the ODIR dataset. We show that integrating real and synthetic data improves classification accuracy and model performance. 

## Methods 

Our process consists of six steps to generate and evaluate synthetic data for ocular disease diagnosis. First, we fine-tune a Stable Diffusion model on specific disease classes. Next, we generate a large synthetic dataset and label it using a fine-tuned VGG19 model. We then reduce the dataset by selecting dominant classes like diabetes and normal using t-SNE. The synthetic data, real data, and selected images are combined into a unified dataset. Finally, we assess the impact of synthetic data on classification accuracy using a pre-trained VGG19 model, aiming to improve performance through data augmentation.

Below is the 6-step algorithm flow used in the study.

![image](https://github.com/user-attachments/assets/cfbd6ad7-ee9f-4ee6-bdad-076a60d0234b)





## Citation 

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

