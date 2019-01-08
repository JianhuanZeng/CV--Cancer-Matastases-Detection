# Cancer-Matastases-Detection
• Develop an assistant tool for physicians that outputs a heatmap showing regions of a gigapixel pathology images likely to contain tumors.<br/>
• Preprocess the large-size image with [Open-slides, OpenCV] for special medical requirements and imbalance data, then use a carefully-designed CNN model to train.

Challenges:
1. For a huge images(tif, more than 100k x 100k pixels), we want to learn as much as details and content. (Multiscale problem) 
2. The data is imbalanced

# Key techniques:
1. Data Preprocessing
Open-slides, OpenCV

2. CNN model
13 Conv layers with (batch normalization + LeakyReLU + some MaxPooling2D)
GloAvgPooling
Dense(1024), dropout=0.25

Loss: "binary_crossentropy”
Optimizer:  AdamOptimizer (lr=0.00005 with patience=10,  lr=0.000001 with patience=2)

# Result
see https://github.com/JianhuanZeng/Cancer-Matastases-Detection/blob/master/Cancer%20Metastases%20Detection.pdf

