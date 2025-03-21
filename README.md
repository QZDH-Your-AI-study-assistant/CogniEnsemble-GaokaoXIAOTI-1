# Dataset Overview

Simplified Chinese README：[简体中文README](README_zh.md)
The dataset is constructed using deepseek-R1 to infer real high school examination questions and past模拟题, with requirements for output format and logical analysis.
## Construction Process
- [Dataset Overview](#dataset-overview)
  - [Construction Process](#construction-process)
  - [Raw Data Acquisition](#raw-data-acquisition)
  - [Inference Process](#inference-process)
  - [Data Cleaning](#data-cleaning)
  - [Notes](#notes)
## Raw Data Acquisition
1. Collected public datasets of real high school examination questions and input them into the inference script.
2. Collected PDF versions of high school examination simulation teaching materials, and used OCR to convert them into TXT format.
3. Converted the TXT format questions into JSON format using chatgpt-4o and relevant prompt words.
## Inference Process
- Imported the original file path into the GenarateCoT.py file of this project, and used DeepSeek-R1 as the inference model to obtain output_result.json.
- Brought the file path of output_result.json into the Post_Process.py file of this project for format adjustment to get output1_result.json.
## Data Cleaning
Basic principles of data cleaning:
1. Questions with inconsistent answers are cleaned and deleted.
2. Questions with consistent answers are retained.
3. Questions with consistent answers but incorrect format are formatted.
For details, see the data cleaning instructions.pdf file in the project.
## Notes
When calling the model, try to use the R1 original model. Untuned distilled models like the open-source deepseek-70b are difficult to correctly infer the corresponding answers. The average number of output tokens for correct answers by deepseek-r1 is 6390, and for incorrect answers is 25600. 

