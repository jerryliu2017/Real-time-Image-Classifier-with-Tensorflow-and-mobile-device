# Real-time-Image-Classifier-with-Tensorflow-and-mobile-device

This is quick work through on the for how to create new Image Classifier with Tensorflow (Google Inception NN), wrap around the model as Android Project(APK):

1. Grab the raw images with fatkun batch image download plugin.
2. Install the tensorflow with python 3.5
3. Retrain the images with the raw images
4. run the manual command to classify the files
5. download and install Android N studio.
6. donwload the Yolo android project from github.
7. build and compile the project with new models.


##############  remove the previous python27, and then Download the python3

C:\>pip3 install --upgrade tensorflow
Collecting tensorflow
  Downloading tensorflow-1.2.0-cp35-cp35m-win_amd64.whl (21.2MB)
    100% |################################| 21.2MB 24kB/s
Collecting six>=1.10.0 (from tensorflow)
  Downloading six-1.10.0-py2.py3-none-any.whl
Collecting protobuf>=3.2.0 (from tensorflow)
  Downloading protobuf-3.3.0.tar.gz (271kB)
    100% |################################| 276kB 1.3MB/s
Collecting backports.weakref==1.0rc1 (from tensorflow)
  Downloading backports.weakref-1.0rc1-py3-none-any.whl
Collecting numpy>=1.11.0 (from tensorflow)
  Downloading numpy-1.13.0-cp35-none-win_amd64.whl (7.8MB)
    100% |################################| 7.8MB 67kB/s
Collecting bleach==1.5.0 (from tensorflow)
  Downloading bleach-1.5.0-py2.py3-none-any.whl
Collecting werkzeug>=0.11.10 (from tensorflow)
  Downloading Werkzeug-0.12.2-py2.py3-none-any.whl (312kB)
    100% |################################| 317kB 1.2MB/s
Collecting markdown==2.2.0 (from tensorflow)
  Downloading Markdown-2.2.0.tar.gz (236kB)
    100% |################################| 245kB 1.3MB/s
Collecting wheel>=0.26 (from tensorflow)
  Downloading wheel-0.29.0-py2.py3-none-any.whl (66kB)
    100% |################################| 71kB 1.8MB/s
Collecting html5lib==0.9999999 (from tensorflow)
  Downloading html5lib-0.9999999.tar.gz (889kB)
    100% |################################| 890kB 517kB/s
Collecting setuptools (from protobuf>=3.2.0->tensorflow)
  Downloading setuptools-36.0.1-py2.py3-none-any.whl (476kB)
    100% |################################| 481kB 796kB/s
Installing collected packages: six, setuptools, protobuf, backports.weakref, numpy, html5lib, bleach, werkzeug, markdown, wheel, tensorflow
  Found existing installation: setuptools 20.10.1
    Uninstalling setuptools-20.10.1:
      Successfully uninstalled setuptools-20.10.1
  Running setup.py install for protobuf ... done
  Running setup.py install for html5lib ... done
  Running setup.py install for markdown ... done
Successfully installed backports.weakref-1.0rc1 bleach-1.5.0 html5lib-0.9999999 markdown-2.2.0 numpy-1.13.0 protobuf-3.3.0 setuptools-36.0.1 six-1.10.0 tensorflow-1.2.0 werkzeug-0.12.2 wheel-0.29.0
You are using pip version 8.1.1, however version 9.0.1 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.

C:\>python -m pip install --upgrade pip
Collecting pip
  Downloading pip-9.0.1-py2.py3-none-any.whl (1.3MB)
    100% |################################| 1.3MB 379kB/s
Installing collected packages: pip
  Found existing installation: pip 8.1.1
    Uninstalling pip-8.1.1:
      Successfully uninstalled pip-8.1.1
Successfully installed pip-9.0.1


######### Download the tensorflow zip files directly, and then run the python 3 command as below to retrain the model.
C:\Users\win7>python tensorflow-master\tensorflow\examples\image_retraining\retrain.py --bottleneck_dir=tf_files\bottlenecks --how_many_training_steps=500 --model_dir=tf_files\inception --output_graph=tf_files\retrained_graph.pb --output_labels=tf_files\retrained_labels.txt --image_dir=tf_files\images
>> Downloading inception-2015-12-05.tgz 100.0%
Successfully downloaded inception-2015-12-05.tgz 88931400 bytes.
Looking for images in 'cars'
Looking for images in 'pets'
2017-06-17 14:37:54.959358: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 14:37:54.959685: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE2 instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 14:37:54.963321: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE3 instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 14:37:54.964932: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 14:37:54.965995: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
Creating bottleneck at tf_files\bottlenecks\cars\17.jpg.txt
2017-06-17 14:37:58.650295: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\framework\op_def_util.cc:332] Op BatchNormWithGlobalNormalization is deprecated. It will cease to work in GraphDef version 9. Use tf.nn.batch_normalization().
Creating bottleneck at tf_files\bottlenecks\cars\24.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\26.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\27.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\28.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\2Q== (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\2Q== (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\2Q== (3).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\2Q== (4).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\2Q== (6).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\2Q==.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\30.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\32.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\33.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\34.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\36.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\39.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\41.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\42.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\43.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\54.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\57.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\59.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\61.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (3).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (4).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (5).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (6).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (7).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (8).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k= (9).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\9k=.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (10).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (100).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (11).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (12).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (14).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (15).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (16).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (17).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (18).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (19).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (20).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (21).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (23).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (24).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (25).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (26).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (27).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (28).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (29).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (3).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (30).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (31).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (32).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (33).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (34).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (35).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (37).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (38).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (39).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (4).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (40).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (43).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (44).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (45).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (46).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (48).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (49).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (5).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (50).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (51).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (54).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (55).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (56).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (57).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (58).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (59).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (6).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (60).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (61).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (62).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (63).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (64).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (65).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (66).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (67).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (69).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (7).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (70).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (71).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (72).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (73).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (75).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (77).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (78).jpg.txt
100 bottleneck files created.
Creating bottleneck at tf_files\bottlenecks\cars\images (8).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (80).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (81).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (82).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (83).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (85).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (86).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (87).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (88).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (89).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (90).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (91).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (93).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (94).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (96).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (97).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (99).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images10.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images11.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images12.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images13.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images14.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images15.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images16.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images18.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images2.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images20.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images21.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images22.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images23.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images25.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images29.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images3.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images31.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images35.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images37.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images4.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images44.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images46.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images47.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images48.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images50.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images51.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images53.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images56.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images58.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images60.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images62.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images63.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images64.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images65.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images67.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images68.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images7.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images70.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images71.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images72.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images73.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images74.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images75.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images76.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images77.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images8.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images9.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\yH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\Z (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\Z (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\Z.jpg.txt
200 bottleneck files created.
300 bottleneck files created.
Creating bottleneck at tf_files\bottlenecks\cars\2Q== (5).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\38.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (13).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (22).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (36).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (41).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (42).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (53).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (74).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (76).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (84).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (92).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (95).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (98).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images49.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images52.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images55.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images66.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\40.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (47).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (52).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (68).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (79).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images (9).jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images1.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images45.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images5.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images6.jpg.txt
Creating bottleneck at tf_files\bottlenecks\cars\images69.jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\2Q== (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\2Q== (3).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\2Q== (5).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\2Q==.jpg.txt
400 bottleneck files created.
Creating bottleneck at tf_files\bottlenecks\pets\9k= (3).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\9k= (4).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\9k= (5).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\9k= (6).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\9k=.jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (10).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (100).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (11).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (13).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (14).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (15).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (16).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (17).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (18).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (19).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (20).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (21).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (22).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (23).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (24).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (25).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (26).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (27).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (28).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (29).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (3).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (31).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (32).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (33).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (34).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (35).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (36).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (37).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (38).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (39).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (4).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (40).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (41).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (42).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (43).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (44).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (45).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (46).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (47).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (48).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (49).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (51).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (52).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (53).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (54).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (55).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (56).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (57).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (59).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (6).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (60).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (61).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (62).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (64).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (65).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (66).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (67).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (68).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (69).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (7).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (70).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (71).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (73).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (74).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (75).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (76).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (77).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (78).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (79).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (8).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (81).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (82).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (83).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (84).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (86).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (87).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (88).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (89).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (9).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (90).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (92).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (93).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (94).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (96).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (97).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (98).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (99).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images.jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\yH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==.jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\Z (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\Z (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\Z (3).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\Z (4).jpg.txt
500 bottleneck files created.
Creating bottleneck at tf_files\bottlenecks\pets\Z (5).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\Z (6).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\Z.jpg.txt
600 bottleneck files created.
Creating bottleneck at tf_files\bottlenecks\pets\2Q== (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\9k= (2).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (12).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (50).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (58).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (63).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (85).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\2Q== (4).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\9k= (1).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (30).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (5).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (72).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (80).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (91).jpg.txt
Creating bottleneck at tf_files\bottlenecks\pets\images (95).jpg.txt
2017-06-17 14:45:33.603486: Step 0: Train accuracy = 100.0%
2017-06-17 14:45:33.603486: Step 0: Cross entropy = 0.603379
2017-06-17 14:45:34.112485: Step 0: Validation accuracy = 100.0% (N=100)
2017-06-17 14:45:38.435487: Step 10: Train accuracy = 100.0%
2017-06-17 14:45:38.435487: Step 10: Cross entropy = 0.247104
2017-06-17 14:45:38.780486: Step 10: Validation accuracy = 100.0% (N=100)
2017-06-17 14:45:42.414490: Step 20: Train accuracy = 99.0%
2017-06-17 14:45:42.414490: Step 20: Cross entropy = 0.184778
2017-06-17 14:45:42.763487: Step 20: Validation accuracy = 100.0% (N=100)
2017-06-17 14:45:46.305488: Step 30: Train accuracy = 99.0%
2017-06-17 14:45:46.305488: Step 30: Cross entropy = 0.122091
2017-06-17 14:45:46.640496: Step 30: Validation accuracy = 100.0% (N=100)
2017-06-17 14:45:50.550493: Step 40: Train accuracy = 99.0%
2017-06-17 14:45:50.550493: Step 40: Cross entropy = 0.105560
2017-06-17 14:45:50.893497: Step 40: Validation accuracy = 100.0% (N=100)
2017-06-17 14:45:54.266556: Step 50: Train accuracy = 97.0%
2017-06-17 14:45:54.266556: Step 50: Cross entropy = 0.125817
2017-06-17 14:45:54.621524: Step 50: Validation accuracy = 100.0% (N=100)
2017-06-17 14:45:58.116499: Step 60: Train accuracy = 98.0%
2017-06-17 14:45:58.116499: Step 60: Cross entropy = 0.107429
2017-06-17 14:45:58.445499: Step 60: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:01.828495: Step 70: Train accuracy = 99.0%
2017-06-17 14:46:01.828495: Step 70: Cross entropy = 0.077289
2017-06-17 14:46:02.169496: Step 70: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:05.587494: Step 80: Train accuracy = 99.0%
2017-06-17 14:46:05.587494: Step 80: Cross entropy = 0.070732
2017-06-17 14:46:05.923556: Step 80: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:09.957501: Step 90: Train accuracy = 99.0%
2017-06-17 14:46:09.958498: Step 90: Cross entropy = 0.073276
2017-06-17 14:46:10.568498: Step 90: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:14.370505: Step 100: Train accuracy = 99.0%
2017-06-17 14:46:14.370505: Step 100: Cross entropy = 0.053394
2017-06-17 14:46:14.702496: Step 100: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:19.026502: Step 110: Train accuracy = 98.0%
2017-06-17 14:46:19.026502: Step 110: Cross entropy = 0.057206
2017-06-17 14:46:19.558501: Step 110: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:25.254015: Step 120: Train accuracy = 100.0%
2017-06-17 14:46:25.254521: Step 120: Cross entropy = 0.043700
2017-06-17 14:46:25.755017: Step 120: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:29.885517: Step 130: Train accuracy = 100.0%
2017-06-17 14:46:29.886039: Step 130: Cross entropy = 0.039866
2017-06-17 14:46:30.219820: Step 130: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:33.868568: Step 140: Train accuracy = 100.0%
2017-06-17 14:46:33.868568: Step 140: Cross entropy = 0.034838
2017-06-17 14:46:34.220560: Step 140: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:37.962390: Step 150: Train accuracy = 98.0%
2017-06-17 14:46:37.968389: Step 150: Cross entropy = 0.044480
2017-06-17 14:46:38.374926: Step 150: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:42.194487: Step 160: Train accuracy = 100.0%
2017-06-17 14:46:42.194929: Step 160: Cross entropy = 0.034725
2017-06-17 14:46:42.580420: Step 160: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:46.124045: Step 170: Train accuracy = 100.0%
2017-06-17 14:46:46.124577: Step 170: Cross entropy = 0.033467
2017-06-17 14:46:46.460053: Step 170: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:49.928556: Step 180: Train accuracy = 99.0%
2017-06-17 14:46:49.929102: Step 180: Cross entropy = 0.046761
2017-06-17 14:46:50.264046: Step 180: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:53.699573: Step 190: Train accuracy = 100.0%
2017-06-17 14:46:53.699573: Step 190: Cross entropy = 0.023408
2017-06-17 14:46:54.039139: Step 190: Validation accuracy = 100.0% (N=100)
2017-06-17 14:46:57.522298: Step 200: Train accuracy = 99.0%
2017-06-17 14:46:57.522836: Step 200: Cross entropy = 0.038298
2017-06-17 14:46:57.908357: Step 200: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:01.644996: Step 210: Train accuracy = 99.0%
2017-06-17 14:47:01.644996: Step 210: Cross entropy = 0.034063
2017-06-17 14:47:02.016841: Step 210: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:06.157460: Step 220: Train accuracy = 99.0%
2017-06-17 14:47:06.157958: Step 220: Cross entropy = 0.038498
2017-06-17 14:47:06.699583: Step 220: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:10.934169: Step 230: Train accuracy = 100.0%
2017-06-17 14:47:10.934169: Step 230: Cross entropy = 0.026691
2017-06-17 14:47:11.274672: Step 230: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:14.976647: Step 240: Train accuracy = 100.0%
2017-06-17 14:47:14.976647: Step 240: Cross entropy = 0.025326
2017-06-17 14:47:15.537648: Step 240: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:19.524648: Step 250: Train accuracy = 100.0%
2017-06-17 14:47:19.524648: Step 250: Cross entropy = 0.026864
2017-06-17 14:47:19.897647: Step 250: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:23.963653: Step 260: Train accuracy = 100.0%
2017-06-17 14:47:23.964717: Step 260: Cross entropy = 0.024290
2017-06-17 14:47:24.300657: Step 260: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:27.983652: Step 270: Train accuracy = 100.0%
2017-06-17 14:47:27.984651: Step 270: Cross entropy = 0.026355
2017-06-17 14:47:28.372713: Step 270: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:32.349657: Step 280: Train accuracy = 99.0%
2017-06-17 14:47:32.350654: Step 280: Cross entropy = 0.028624
2017-06-17 14:47:32.867688: Step 280: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:36.746652: Step 290: Train accuracy = 100.0%
2017-06-17 14:47:36.746652: Step 290: Cross entropy = 0.017837
2017-06-17 14:47:37.104686: Step 290: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:40.926655: Step 300: Train accuracy = 100.0%
2017-06-17 14:47:40.926655: Step 300: Cross entropy = 0.019211
2017-06-17 14:47:41.284716: Step 300: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:44.727656: Step 310: Train accuracy = 100.0%
2017-06-17 14:47:44.728657: Step 310: Cross entropy = 0.015054
2017-06-17 14:47:45.061690: Step 310: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:48.747663: Step 320: Train accuracy = 100.0%
2017-06-17 14:47:48.747663: Step 320: Cross entropy = 0.020074
2017-06-17 14:47:49.078720: Step 320: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:52.466665: Step 330: Train accuracy = 98.0%
2017-06-17 14:47:52.466665: Step 330: Cross entropy = 0.032087
2017-06-17 14:47:52.804658: Step 330: Validation accuracy = 100.0% (N=100)
2017-06-17 14:47:56.498660: Step 340: Train accuracy = 100.0%
2017-06-17 14:47:56.499659: Step 340: Cross entropy = 0.018699
2017-06-17 14:47:56.912720: Step 340: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:00.490724: Step 350: Train accuracy = 100.0%
2017-06-17 14:48:00.491713: Step 350: Cross entropy = 0.018662
2017-06-17 14:48:00.829663: Step 350: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:04.468695: Step 360: Train accuracy = 100.0%
2017-06-17 14:48:04.469668: Step 360: Cross entropy = 0.014423
2017-06-17 14:48:04.825662: Step 360: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:08.641667: Step 370: Train accuracy = 98.0%
2017-06-17 14:48:08.641667: Step 370: Cross entropy = 0.030979
2017-06-17 14:48:09.018719: Step 370: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:13.011670: Step 380: Train accuracy = 99.0%
2017-06-17 14:48:13.011670: Step 380: Cross entropy = 0.029852
2017-06-17 14:48:13.364671: Step 380: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:17.310697: Step 390: Train accuracy = 100.0%
2017-06-17 14:48:17.311678: Step 390: Cross entropy = 0.015144
2017-06-17 14:48:17.643726: Step 390: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:21.289725: Step 400: Train accuracy = 100.0%
2017-06-17 14:48:21.290667: Step 400: Cross entropy = 0.023072
2017-06-17 14:48:21.633732: Step 400: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:25.325668: Step 410: Train accuracy = 100.0%
2017-06-17 14:48:25.326670: Step 410: Cross entropy = 0.018472
2017-06-17 14:48:25.657675: Step 410: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:29.442668: Step 420: Train accuracy = 100.0%
2017-06-17 14:48:29.442668: Step 420: Cross entropy = 0.015604
2017-06-17 14:48:29.859676: Step 420: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:33.498703: Step 430: Train accuracy = 100.0%
2017-06-17 14:48:33.498703: Step 430: Cross entropy = 0.014697
2017-06-17 14:48:33.857704: Step 430: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:37.902672: Step 440: Train accuracy = 100.0%
2017-06-17 14:48:37.902672: Step 440: Cross entropy = 0.012119
2017-06-17 14:48:38.392673: Step 440: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:41.837675: Step 450: Train accuracy = 100.0%
2017-06-17 14:48:41.837675: Step 450: Cross entropy = 0.013888
2017-06-17 14:48:42.194707: Step 450: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:45.812675: Step 460: Train accuracy = 99.0%
2017-06-17 14:48:45.813735: Step 460: Cross entropy = 0.029362
2017-06-17 14:48:46.145706: Step 460: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:49.767677: Step 470: Train accuracy = 99.0%
2017-06-17 14:48:49.768737: Step 470: Cross entropy = 0.025880
2017-06-17 14:48:50.115682: Step 470: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:53.495733: Step 480: Train accuracy = 100.0%
2017-06-17 14:48:53.495733: Step 480: Cross entropy = 0.015245
2017-06-17 14:48:53.851708: Step 480: Validation accuracy = 100.0% (N=100)
2017-06-17 14:48:57.551686: Step 490: Train accuracy = 99.0%
2017-06-17 14:48:57.551686: Step 490: Cross entropy = 0.019618
2017-06-17 14:48:57.910676: Step 490: Validation accuracy = 100.0% (N=100)
2017-06-17 14:49:02.782680: Step 499: Train accuracy = 100.0%
2017-06-17 14:49:02.782680: Step 499: Cross entropy = 0.019774
2017-06-17 14:49:03.486681: Step 499: Validation accuracy = 100.0% (N=100)
Final test accuracy = 100.0% (N=50)
Converted 2 variables to const ops.


C:\Users\win7>cd tf_files

C:\Users\win7\tf_files>dir
 Volume in drive C is Windows
 Volume Serial Number is 44B2-EF27

 Directory of C:\Users\win7\tf_files

06/17/2017  03:00 PM    <DIR>          .
06/17/2017  03:00 PM    <DIR>          ..
06/17/2017  02:42 PM    <DIR>          bottlenecks
06/17/2017  02:37 PM    <DIR>          images
06/17/2017  02:37 PM    <DIR>          inception
06/17/2017  03:05 PM             1,163 label_image.py
06/17/2017  02:49 PM        87,431,992 retrained_graph.pb
06/17/2017  02:49 PM                10 retrained_labels.txt
               3 File(s)     87,433,165 bytes
               5 Dir(s)  576,689,295,360 bytes free

C:\Users\win7\tf_files>
C:\Users\win7\tf_files>
C:\Users\win7\tf_files>python label_image.py images\pets\dabao.jpg
2017-06-17 15:10:40.892676: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 15:10:40.892997: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE2 instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 15:10:40.896763: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE3 instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 15:10:40.897806: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 15:10:40.898943: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\platform\cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
2017-06-17 15:10:44.102044: W c:\tf_jenkins\home\workspace\release-win\m\windows\py\35\tensorflow\core\framework\op_def_util.cc:332] Op BatchNormWithGlobalNormalization is deprecated. It will cease to work in GraphDef version 9. Use tf.nn.batch_normalization().
pets (score = 0.98294)
cars (score = 0.01706)

C:\Users\win7\tf_files>



Reference:
https://chrome.google.com/webstore/detail/fatkun-batch-download-ima/nnjjahlikiabnchcpehcpkdeckfgnohf?hl=en
https://github.com/natanielruiz/android-yolo

https://github.com/tensorflow/tensorflow
