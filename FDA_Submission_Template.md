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

<center>
	<img src="img/Algorithmflowchart.png">>
</center>>

**DICOM Checking Steps:**

1. This DICOM is a digital radiography or not?
2. This DICOM is shot in [PA, AP] or not?

**Preprocessing Steps:**

1. Initial a new ImageGenerator
2. Resize images
3. Generate img flow based on the batch_size 

**CNN Architecture:**

<center>
	<img src="img/CNNArichitecture.png">
</center>>

### 3. Algorithm Training

**Parameters:**
* Types of augmentation used during training
* Batch size
* Optimizer learning rate
* Layers of pre-existing architecture that were frozen
* Layers of pre-existing architecture that were fine-tuned
* Layers added to pre-existing architecture

* Type of augmentations:

	rotation,
	width_shift_range,
	height_shift_range,
	shear_range,
	zoom_range,
	rescale

* Batch_size:

	32

* Optimizer learning rate:

	0.001

* Layers of pre-existing architecture that were frozen:

	[:-2]

* Layers of pre-existing architecture that were fine-tuned:

	[-2: ]

* Layers added to pre-existing architecture:

	1. Flatten Layer
	2. Dense Layer (1024)
	3. Dropout Layer(0.5)
	4. Dense Layer (512)
	5. Dropout Layer (0.5)
	6. Dense Layer (512)
	7. Dropout Layer (0.5)
	8. Dense Layer (0.5)
	9. Output Layer (1)

<center>
	<img src="img/traininghistoryaccuracy.png">
	<img src="img/traininghistoryloss.png">
	<img src="img/P-Rcurve.png">
</center>

**Final Threshold and Explanation:**

As the P-R plot above, I take 0.5 as my threshold. It is the most balanced value for Precision, Recall, and F1 score.

### 4. Databases
 (For the below, include visualizations as they are useful and relevant)

The dataset include people aged from 1 to 95.

<center>
	<img src="img/AgeDist.png">
</center>

Including diseases:

<center>
	<img src="img/findinglabels.png">
</center>

And the corrlations among these diseases:

<center>
	<img src="img/heat.png">
</center>

**Description of Training Dataset:** 

Contains 2288 rows of valid data, 1144 valid data contains Penumonia.

<center>
	<img src="img/trainingseq.png">
</center>

**Description of Validation Dataset:** 

Contains 1430 rows of valid data, 286 valid data contains Pneumonia.

### 5. Ground Truth

Labeled by experienced radiologists.

### 6. FDA Validation Plan

**Patient Population Description for FDA Validation Dataset:**

From 1 year old to 95 years old. 
Male : Female = 1.41 : 1
