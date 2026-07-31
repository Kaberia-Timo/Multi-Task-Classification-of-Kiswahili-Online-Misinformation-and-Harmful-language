\# Multi-task Misinformation Detection for Low-Resource Swahili



A reproducible deep learning pipeline for multi-task learning on \*\*Swahili misinformation detection\*\* and \*\*Swahili hate speech detection\*\* using shared transformer representations.



This repository accompanies the research project investigating whether \*\*joint multi-task learning\*\* can improve misinformation detection by leveraging knowledge from a related hate speech detection task in a low-resource language.



\---



\## Overview



The project develops and evaluates two multi-task transformer models:



1\. \*\*Baseline Multi-task Model\*\*

&#x20;  - Equal task weighting

&#x20;  - Joint learning of misinformation and hate speech



2\. \*\*Misinformation-Tuned Multi-task Model\*\*

&#x20;  - Increased optimisation emphasis on misinformation detection

&#x20;  - Same architecture as the baseline

&#x20;  - Different task-loss weighting strategy



The experiments use:



\- \*\*PolitikWeli\*\* (Swahili misinformation dataset)

\- \*\*AfriHate\*\* (Swahili hate speech dataset)



Both datasets are harmonised into a unified multi-task training dataset while preventing data leakage and ensuring reproducibility.



\---



\## Repository Structure



```text

multitask-misinformation-detection/

│

├── data/

│   ├── raw/

│   └── processed/

│

├── notebooks/

│   ├── 01\_politikweli\_prepare.ipynb

│   ├── 02\_afrihate\_prepare.ipynb

│   ├── 03\_build\_multitask\_dataset.ipynb

│   ├── 04\_baseline\_training.ipynb

│   └── 05\_misinformation\_tuned\_training.ipynb

│

├── models/

│   ├── baseline/

│   └── misinformation\_tuned/

│

├── reports/

├── docs/

└── src/

```



\---



\## Workflow



The notebooks should be executed in the following order.



\### Notebook 1



\*\*01\_politikweli\_prepare.ipynb\*\*



Purpose



\- Load hydrated PolitikWeli datasets

\- Clean and harmonise records

\- Construct binary misinformation labels

\- Perform stratified train/validation/test split

\- Export frozen datasets



Outputs



```

data/processed/politikweli/

```



\---



\### Notebook 2



\*\*02\_afrihate\_prepare.ipynb\*\*



Purpose



\- Download AfriHate from Hugging Face

\- Harmonise labels

\- Clean text

\- Create train/validation/test splits

\- Export frozen datasets



Outputs



```

data/processed/afrihate/

```



\---



\### Notebook 3



\*\*03\_build\_multitask\_dataset.ipynb\*\*



Purpose



\- Validate dataset compatibility

\- Construct multi-task targets

\- Merge frozen datasets

\- Generate final multi-task datasets



Outputs



```

data/processed/multitask/

```



\---



\### Notebook 4



\*\*04\_baseline\_training.ipynb\*\*



Purpose



Train the baseline multi-task transformer model using equal task weighting.



Outputs



```

models/baseline/

```



\---



\### Notebook 5



\*\*05\_misinformation\_tuned\_training.ipynb\*\*



Purpose



Train the misinformation-focused multi-task model using modified task-loss weighting.



Outputs



```

models/misinformation\_tuned/

```



\---



\## Datasets



\### PolitikWeli



Task



Binary misinformation detection.



Classes



\- Not Misinformation

\- Misinformation



Raw files



```

data/raw/politikweli/



hydrated\_valid\_swa\_master.csv

hydrated\_valid\_swa\_eng\_master.csv

```



\---



\### AfriHate



Task



Three-class hate speech classification.



Classes



\- Normal

\- Abusive

\- Hate



The dataset is automatically downloaded from Hugging Face during preprocessing.



\---



\## Models



The project evaluates two models.



| Model | Description |

|--------|-------------|

| Baseline | Equal task weighting |

| Misinformation-tuned | Increased optimisation weight for misinformation detection |



Both models share:



\- XLM-RoBERTa encoder

\- Shared transformer backbone

\- Separate task-specific classification heads



\---



\## Installation



Clone the repository.



```bash

git clone https://github.com/<username>/multitask-misinformation-detection.git



cd multitask-misinformation-detection

```



Create an environment.



```bash

pip install -r requirements.txt

```



or



```bash

conda env create -f environment.yml

```



\---



\## Reproducibility



Random seeds are fixed throughout the project.



Dataset splits are frozen and exported.



Training metadata is saved for every experiment.



Model checkpoints are stored automatically.



\---



\## Outputs



The repository produces:



\### Processed datasets



```

data/processed/

```



\### Trained models



```

models/

```



\### Evaluation results



\- Classification reports

\- Confusion matrices

\- Evaluation metrics

\- Training history

\- Training configuration



\---



\## Citation



If you use this repository in academic work, please cite the associated dissertation.



\---



\## License



This project is released under the MIT License.



See the LICENSE file for details.



\---



\## Author



\*\*Timothy\*\*



Master's Research Project



Multi-task Learning for Low-Resource Swahili Misinformation Detection

