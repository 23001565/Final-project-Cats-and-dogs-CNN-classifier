
The `notebooks/` folder contains all project notebooks for the Cats vs Dogs CNN classification project.

1. **compact_functions_to_run.ipynb**
   - Wraps the main functions for training strategies and testing into compact functions.
   - Downloads required data from Google Drive (dataset `pets0` and checkpoints `mods`).
   - Includes four main functions:
     - `SimCLR pretraining`
     - `Finetuning for SimCLR`
     - `Knowledge Distillation (KD)`
     - `Testing models`
   - Trainings are GPU-intensive and can take a long time.

2. **SimCLR_training_results.ipynb**
   - Contains detailed SimCLR training and finetuning results.
   - Shows results for train set sizes: 10,000; 6,000; 3,000.
   - Some trainings were paused and resumed, so there are moderate duplications in the code.

3. **KD_results.ipynb**
   - Details Knowledge Distillation (KD) training and results.
   - Covers the same three training set sizes.

4. **Testing_models_results.ipynb**
   - Evaluates the trained models on the test set (5,000 samples).
   - Reports accuracy, precision, recall, and other metrics.

5. **Visualize-effects-of-libs-and-models.ipynb**
   - Shows the architectures of MobileNetV2 and ResNet50.
   - Visualizes SimCLR augmentations using the Lightly module.
   - Compares feature maps learned by MobileNetV2 and ResNet50.

## Run Notebooks in Google Colab

Click the links below to open and run the notebooks directly in Colab:
1. [compact_functions_to_run](https://colab.research.google.com/github/23001565/Final-project-Cats-and-dogs-CNN-classifier/blob/master/notebooks/compact_functions_to_run.ipynb)
2. [SimCLR_training_results](https://colab.research.google.com/github/23001565/Final-project-Cats-and-dogs-CNN-classifier/blob/master/notebooks/SimCLR_training_results.ipynb)
3. [KD_results](https://colab.research.google.com/github/23001565/Final-project-Cats-and-dogs-CNN-classifier/blob/master/notebooks/KD_results.ipynb)
4. [Testing_models_results](https://colab.research.google.com/github/23001565/Final-project-Cats-and-dogs-CNN-classifier/blob/master/notebooks/Testing_models_results.ipynb)
5. [Visualize-effects-of-libs-and-models](https://colab.research.google.com/github/23001565/Final-project-Cats-and-dogs-CNN-classifier/blob/master/notebooks/Visualize-effects-of-libs-and-models.ipynb)

or access via the drive folder:
   [drive link](https://drive.google.com/drive/folders/1eoQ2REdIvF-qhs9Ozx2E0LV29fD3ZTvc?usp=drive_link)
   
## Notes on Checkpoints (“mods” folder in the project drive)

I renamed some checkpoint files for consistency.  
(This may cause a few `save_path` entries in **SimCLR_training_results.ipynb** to be outdated,  
but all other notebooks should remain unaffected.)

### SimCLR Pretraining
Filename format:
`mobilenet_sim_<train-set-size>_<extra-tag>.pth`

**extra-tag options:**
- `"epoch"` — periodic checkpoint saves  
- `"cont"` or *empty* — best checkpoints  
  *(Some training runs were interrupted and later resumed; resumed best checkpoints are marked with `"cont"`. Treat them as the final best checkpoints.)*

Note:  
The checkpoints referenced in the report (see **Testing_models_results.ipynb** for exact selections)   
are not always the *final* best checkpoints.  
In some cases, earlier checkpoints achieved similar overall accuracy but showed **better per-class and among-class balance**  
in metrics such as precision and recall.

### Finetuning for SimCLR
Filename format:  
`student_finetuned_<train-set-size>_<extra-tag>.pth`

### Knowledge Distillation
- Teacher (fine-tuned on task-specific data):  only one checkpoint
  `resnet_finetune_only.pth`
- Students:  
  `only_distilled_student_<train-set-size>_<extra-tag>.pth`

