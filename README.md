# Cancer-Matastases-Detection
• Develop an assistant tool for physicians that outputs a heatmap showing regions of a gigapixel pathology images likely to contain tumors.<br/>
• Preprocess the large-size image with [Open-slides, OpenCV] for special medical requirements and imbalance data, then use a carefully-designed CNN model to train.<br/>
similar to a Kaggle competition,see: https://www.kaggle.com/c/histopathologic-cancer-detection

Challenges:
1. For a huge images(tif, more than 100k x 100k pixels), we want to learn as much as details and content. (Multiscale problem) 
2. The data is imbalanced

# Key techniques:
1. Data Preprocessing<br/>
Open-slides, OpenCV

2. CNN model:<br/>
• 13 Conv layers with (batch normalization + LeakyReLU + some MaxPooling2D)<br/>
• GloAvgPooling<br/>
• Dense(1024), dropout=0.25<br/>

Loss: "binary_crossentropy”<br/>
Optimizer:  AdamOptimizer (lr=0.00005 with patience=10,  lr=0.000001 with patience=2)

# Result
see https://github.com/JianhuanZeng/Cancer-Matastases-Detection/blob/master/Cancer%20Metastases%20Detection.pdf

# Reference
Detecting Cancer Metastases on Gigapixel Pathology Images by Yun Liu1?, Krishna Gadepalli1, Mohammad Norouzi1, George E. Dahl1, Timo Kohlberger1, Aleksey Boyko1, Subhashini Venugopalan2??, Aleksei Timofeev2, Philip Q. Nelson2, Greg S. Corrado1, Jason D. Hipp3, Lily Peng1, and Martin C. Stumpe1 <br/>
also see: https://github.com/JianhuanZeng/Cancer-Matastases-Detection/blob/master/Detecting%20Cancer%20Metastases%20on%20Gigapixel%20Pathology%20Images.pdf


