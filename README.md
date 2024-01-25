# Staff Recognition with Computer vision
## Staff Detection System Design

This staff detection system is made up with 3 different components, components are listed in order.

* Human detection component
* Staff tag detection component
* Torso detection component
* Filtering of detection noises

## Human Detection component

Yolo v7 was used to detect humans. The output of this component are cropped images of each instance of detected humans. 

## Staff Tag detection component

Another Yolo v7 model was trained to detect and recognise the staff’s tag. Around 200 images are extracted from the previous component and manually labelled to train this model.

## Torso detection component

Torso detection component is used to filter out garbage detection from Staff Tag detection component. Yolo v7 pose estimation model or key point model is used in this component to identify the torso bounding box of human. Below are the example output of the model. The torso bounding box is identified as area from left shoulder until the right hips. The output is coordination of torso bounding box.

## Filtering of detection noises

The detection of tag outside of the torso bounding box coordination is considered as a false prediction. This could filter out many inaccurate predictions made from the second component staff tag detection component. 

## Future improvement

Implement deep sort for object tracking and counting
Train staff tag detection model using output from torso detection model 

