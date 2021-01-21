# MA797-Final-Project
Machine Learning final project: animal image classification using transfer learning. But with a twist!

Note: This was technically a group project, but I did all of the coding, almost all of the writing, and was the only member to present. To not throw my other team-members under the bus, their names have been removed.

Check out the linked Google Colab Notebook or the final paper to get a better sense of why this project was much more difficult than it may seem.

Some details: 

The original dataset was 10GB in size, consisting of 25,000 high resolution labeled images of 20 different species of animals, captured at camera traps in the Netherlands and Panama (http://lila.science/datasets/missouricameratraps).

The data was highly imbalanced and non-uniform, with a mix of different camera resolutions, black and white infrared images, full colour images, and high degrees of similarity between some of the different species.

Uniquely, the images were presented in sequences of snapshots, ranging from 3 images to 305, taken a few seconds apart as the animal triggered a motion sensor. This posed a unique challence, since many labeled images contained an animal that had just walked out of frame. There was also a high degree of background similarity for images in the same sequence.

This posed a unique opportunity to develop new algorithms to classify entire sequences of images, based on either which image in a sequence was classified with the highest confidence, or a proprietary way of measuring how much confidence levels varied from the expected mean. See Section 4 of the MA_797_Project report for details.

In summary, using these new metrics, we were able to increase classification accuracy from 64% to 80% on out-of-sample images using traditional transfer learning with VGG-16, image augmentation, and a few other tricks, like a custom training set. See the full paper for details!

The complete cleaned dataset (B/W images removed, metadata borders trimmed, custom training set, see Section 3.1 for details) is available here: https://drive.google.com/file/d/1SqYQQZBN3QGsR3i0Zmk0MyVrrKy-JnzF/view?usp=sharing

