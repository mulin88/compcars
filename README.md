# compcars

Train/build car verification model based on Compcars dataset
 (Pytorch CNN approaches) 

Current implementations included:
1. Dataset pre-processing.
   
  - Dataset will be divided by three parts:
  - Part I:  for car image classification training/validation
  - Part II: for car image feature exracting
  - Part III: for car verification 

2. Train a car classification model.
  - Dataset: Part I
  - DL: GoogleNet Inception V3(with pretrained=imagenet)
  - Tool: Pytorch
  - Result: within 100 epoches, train accuracy is about 93%, valid accurary is about 71% (as of Dec 4th)

3. From above 2 classication model, fetch final FC layer features [2048 x 1] for another verification dataset
  - Dataset: Part II
  - DL: above 2 model
  - Tool: Pytorch
  - Result: features dataset for about 16010 images, which are [16010 x 2048]

4. PCA to reduce above 3 from dimensions 2048 to 20
  - Dataset: above 3's output
  - Tool: scikit-learn
  - Result: dataset of [16010 x 20]

5. Joint Bayesian training  
  - Dataset: above 5 (together with original labels)
  - Tool: python 
  - Result: Bayesian model    

6. Car verification
  - Dataset: Part III
  - DL: model from above 2 
  - and  model from above 6
  - Tool: Pytorch
  - Result: 



