A project for school in which we use OpenCV and Tensorflow to train a CNN model for detecting traffic light colours, and then predicting on a different set of images to label them with the colour detected.

This project was completed for CVI course at Seneca, supervised by professor Savita Seharawat.
The dataset was acquired from kaggle.com.

The CNN architechture includes convolutional, max-pooling, dropout, and dense layers compiled with the Adam optimizer and categorical cross-entropy loss function. It is trained on the prepared dataset for 75 epochs with a validation split to monitor performance.

Once the model is trained, it is uses YOLO to detect traffic lights in the non-labeled images. It outputs bounding boxes around the detected objects. The detected lights are cropped from the original image using the bounding box coordinates. The cropped images are resized to 32x32 pixels. The resized images are normalized to the range [0,1]. The normalized images are fed into the trained CNN model, which outputs probabilities for each colour class. The class with the highest probability is selected as the predicted colour. The predicted colour is used to label the detected traffic light in the image. A rectangle is drawn around the traffic light and the predicted colour label is displayed.
