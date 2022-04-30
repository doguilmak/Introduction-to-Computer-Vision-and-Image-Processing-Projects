# Mask or No Mask

## Brief Explanation of Pre-processing

Generating **TFRecord is Tensorflow’s binary storage format**. Using a binary file format for storage of your data can have a significant impact on the performance of your import pipeline as a consequence on the training time of your model. 

Then, the images will be split as **70%**.

    from tfrecord import create_tf_record, displaydetectedobject
	image_files = [image for image in annotations["annotations"].keys()]
	label_map = label_map_util.get_label_map_dict(LABEL_MAP_PATH)
    
    random.seed(42)
    random.shuffle(image_files)
    num_train = int(0.7 * len(image_files))
    train_examples = image_files[:num_train]
    val_examples = image_files[num_train:]

## Selecting the Model

We uploaded your object detection model configuration which is **MobileNet V1** from tensorflow.org. There are also many other object detection models available. If you are interested go to this link ([https://github.com/tensorflow/models/blob/7c2ff1afc4423266223bcd50cba0ed55aca826c8/research/object_detection/g3doc/tf1_detection_zoo.md](https://github.com/tensorflow/models/blob/7c2ff1afc4423266223bcd50cba0ed55aca826c8/research/object_detection/g3doc/tf1_detection_zoo.md)) and you will find many other models. Training a model from scratch can take long hours and tons of data. So, we helped you in reducing that effort by training the MobileNet model with a checkpoint.

The model that will be trained is the SSD MobileNet architecture. SSD MobileNet models have very small file sizes and can execute very quickly, compromising little accuracy, which makes it perfect for running in the browser.

**It may take a few minutes for the page to open. Please wait to complete your classification process. You need webcam to make prediction on yourself.**

Link to test the classifier model: Link to test the classifier model: <a href="https://mark-or-no-mask-demo-625af0f8856925f4b8ebd897.mr4ngdkhlwg.eu-gb.codeengine.appdomain.cloud/" target="_blank">Classification via IBM Cloud</a>
