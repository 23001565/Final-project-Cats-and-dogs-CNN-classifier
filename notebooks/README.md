
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

5. **05_Visualize-effects-of-libs-and-models.ipynb**
   - Shows the architectures of MobileNetV2 and ResNet50.
   - Visualizes SimCLR augmentations using the Lightly module.
   - Compares feature maps learned by MobileNetV2 and ResNet50.

