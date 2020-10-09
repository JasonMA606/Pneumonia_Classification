# FDA  Submission

**Your Name:**
Zhicheng Ma
**Name of your Device:**
Pneumonia Detection Algorithm
## Algorithm Description 

### 1. General Information

**Intended Use Statement:** 
As a CADx devide to assist the radiologist in the detection of Penumonia.
**Indications for Use:**
The algorithm is indicated to used for people from 1 to 95 years old who have taken an Xray image in AP or PA position.
**Device Limitations:**
The algorithm does not work for people under 1-year-old or beyond 95 years old. The algorithm only works for Xray images were taken by AP or PA position.

### 2. Algorithm Design and Function

<< Insert Algorithm Flowchart >>

**DICOM Checking Steps:**

**Preprocessing Steps:**

**CNN Architecture:**


### 3. Algorithm Training

**Parameters:**
* Types of augmentation used during training
* Batch size
* Optimizer learning rate
* Layers of pre-existing architecture that were frozen
* Layers of pre-existing architecture that were fine-tuned
* Layers added to pre-existing architecture

<< Insert algorithm training performance visualization >> 

<< Insert P-R curve >>

**Final Threshold and Explanation:**

### 4. Databases
 (For the below, include visualizations as they are useful and relevant)

**Description of Training Dataset:** 


**Description of Validation Dataset:** 


### 5. Ground Truth



### 6. FDA Validation Plan

**Patient Population Description for FDA Validation Dataset:**

**Ground Truth Acquisition Methodology:**

**Algorithm Performance Standard:**
