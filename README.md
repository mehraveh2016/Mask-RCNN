# Mask-RCNN

**	Mask RCNN is extension of  Faster RCNN**

•	Mask R-CNN has an additional branch for predicting segmentation masks on each Region of Interest (RoI) in a pixel-to pixel manner.
•	Faster R-CNN is not designed for pixel-to-pixel alignment between network inputs and outputs.
•	Faster R-CNN has two outputs:
o	For each candidate object, a class label and a bounding-box offset.
•	Mask R-CNN has three outputs:
o	For each candidate object, a class label and a bounding-box offset.
o	Third output is the object mask
•	Both Mask R-CNN and Faster R-CNN have a branch for classification and bounding box regression.
•	Both use ResNet 101 architecture to extract features from image.
•	Both use Region Proposal Network(RPN) to generate Region of Interests(RoI)

	Architecture

Mask R-CNN model is divided into two parts:
•	Region proposal network (RPN) to proposes candidate object bounding boxes.
•	Binary mask classifier to generate mask for every class
•	Image is run through the CNN to generate the feature maps.
•	Region Proposal Network(RPN) uses a CNN to generate the multiple Region of Interest(RoI) using a lightweight binary classifier. It does this using 9 anchors boxes over the image. The classifier returns object/no-object scores. Non Max suppression is applied to Anchors with high objectness score.
•	The RoI Align network outputs multiple bounding boxes rather than a single definite one and warp them into a fixed dimension.
•	Warped features are then fed into fully connected layers to make classification using SoftMax and boundary box prediction is further refined using the regression model.
•	Warped features are also fed into Mask classifier, which consists of two CNN’s to output a binary mask for each RoI. Mask Classifier allows the network to generate masks for every class without competition among classes.

the code structure is :

![mask](https://user-images.githubusercontent.com/17246929/180650285-3fabe7cc-d41d-485e-bb42-32e25c852631.jpg)

My project is described in a report, along with the results. Feel free to contact me if you have any questions.
