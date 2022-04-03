<div align="center">

# Image quality detection  using Machine Learning
</div>

## STEPS FOR EXECUTING THE FILES

<b>STEP-1:</b> After installing all the dependencies, make sure that the dataset contains images in below mentioned paths<br>
<ul>
  <li>CERTH_ImageBlurDataset/TrainingSet/<br>
    <ul>
      <li>Undistorted/</li>
      <li>Naturally-Blurred/</li>
      <li>Artificially-Blurred/</li>
    </ul>
  </li>
  <li>CERTH_ImageBlurDataset/EvaluationSet/ <br>
    <ul>
      <li>DigitalBlurSet/</li>
      <li>NaturalBlurSet/</li>
      <li>DigitalBlurSet.xlsx</li>
      <li>NaturalBlurSet.xlsx</li>
    </ul
  </li>
</ul>

<b>STEP-:2</b> After completion of above two steps, for processing the images and generation of features, execute "<b>image_processing_and_feature_generation.py</b>" file in command prompt.<br><br>
**NOTE:** Executing this file will take some time, this code is already executed and the generated csv files are already present in the folder. I recommend to skip execution of this step and proceed with next step.

```python
python image_processing_and_feature_generation.py
```
After executing the above file, you can notice two csv files in current working directory "train.csv" and "validation.csv".

<b>STEP-3:</b> After executing the above command, execute "<b>train_model.py</b>" in command prompt<br>

```python
python train_model.py
```
After executing the above file, you can notice two pickle files in current working directory "XGBoost.pkl" and "voting_model.pkl".

<b>STEP-4:</b> After executing the above command, execute "<b>validation.py</b>" in command prompt to get the scores on evaluation dataset<br>

```python
python validation.py
```
After executing the above file, you can notice a pickle file "<b>Final_Model.pkl</b>" which got the highest validation accuracy.

## RESULT
After execution of all steps, a model with 88% accuracy on evaluation set was generated. Both the XGBoost and Voting Classifier models performed well with same accuracy.<br>
"Final_Model.pkl" is the final version of the model and can be used for predicting whether a image is blur image or clear image.
