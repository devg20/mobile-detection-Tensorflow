# mobile-detection-Tensorflow

## Mobile/ Phone Detection using ssd_inception_v2_coco

Follow the steps to setup the files for training the model.

1. Create a folder named "tensorflow1" in C.
Download or clone: https://github.com/tensorflow/models into the "tensorflow1" models.

2. Copy the contents in images folder in this github repo and paste it in "C:\tensorflow1\models\research\object_detection\images".
   The images folder has test and train folders which contain images with labels. The folder also has files "train.csv" and "test.csv"
   which contain image file information and labels in a csv format.
   
3. Copy contents in data folder in this github repo and paste it in "C:\tensorflow1\models\research\object_detection\data".
   The data folder has the labelmap.pbtxt file in which all classes(objects to be detected) are defined in a proper syntax. The folder
   also has the files "test.record" and "train.record" which store data in binary format for faster loading and processing.

4. Copy the file "ssd_inception_v2_coco.config" in this github repo and paste it in "C:\tensorflow1\models\research\object_detection".
   This is the config file which has information of the layers, declarations of the file locations to be used(like labelmap.pbtxt, train.record, test.record,
   model checkpoint i.e. ssd_inception_v2_coco_2018_01_28/model.ckpt) and also defines the number of classes.

5. Click the link below to download model checkpoint used in this project: 
   http://download.tensorflow.org/models/object_detection/ssd_inception_v2_coco_2018_01_28.tar.gz
   
   You can check out other available models at: https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1_detection_zoo.md

6. Extract the download "ssd_inception_v2_coco_2018_01_28.tar.gz" in "C:\tensorflow1\models\research\object_detection" directory.

7. To start training the model, open a terminal in this "C:\tensorflow1\models\research\object_detection" directory. 
   
   Now run the following command to run the "train.py" file located in "C:\tensorflow1\models\research\object_detection":
   
   ### python train.py --logtostderr --train_dir= training/ --pipeline_config_path=ssd_inception_v2_coco.config
  
8. Post Training, to export inference graph of the model,  open a terminal in this "C:\tensorflow1\models\research\object_detection" directory.

   Now run the following command to execute the "export_inference_graph.py" file in "C:\tensorflow1\models\research\object_detection":
  
   ### python export_inference_graph.py --input_type image_tensor --pipeline_config_path ssd_inception_v2_coco.config --checkpoint_path training/model.ckpt-<latest saved 
   ### training step number> --inference_graph_path <model-name-any>.pb

9. To test the model locally, run the webcam_detection.py file in this repo(Update the lines 20, 32, 40, 42 accordingly).
   Open a terminal in "C:\tensorflow1\models\research\object_detection" and run the following command:
   
   ### python webcam_detection.py
    
    
Finally if you want save the hardwork, you can download my inference graph folder "phone_det_graph" in this repo. :).
 
        

