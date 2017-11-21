Paper title: SqueezeDet: Unified, Small, Low Power Fully Convolutional Neural Networks for Real-Time Object Detection for Autonomous Driving


Summary:
The paper proposes object detector based on squeezenet targeting autonomous driving for speed,memory and power consumption with SoA in results over KITTI
The method is in line with yolo based end to end single shot detector with mutiple loss.
The paper states the target as "While recent research has been primarily focused on improving accuracy, for actual deployment in an autonomous vehicle, there are other issues of image object detection that are equally critical."

After strengthening the SqueezeNet model with additional layers followed by ConvDet, the total model size is still less than 8MB( this is debatable based on number of classes)
Unlike number of classes through fully connected layer in yolo, squezedet uses fully cnn with training involving anchor tuning.
The loss function is multi component in nature (see the paper) with results evaluated on KITTI.

Contrbution:
Squeezent based detector and loss function with multi components unlike SSD and YOLO

Novel elements:
Loss function and squeezenet for object detector

Failures:
The paper evaluations are biased  more towards kitti with no other results.
Typical experimental observation from my side is that anchors play a key role and the size of image is also important.
The detection quality on other datasets are not so good as mentioned for KITTI results, further the kITTI models and other trained models suffer from bbox diplacement issue(fixable)
Added paper doesnt specify any intution on how the loss function was decided. 
The paper says even though it is deriived out of yOLO due to smaller filter size, the feature maps are big and better helps in detection qualifies for derived wor.
Mostly the papers claim on memory size doesnt make senseexpecially only the experiments are with three classes. During practical experiment  found that for 20 class, the model is around 25-30MB again requiring compression. 


Notations: Nothing new, easy to follow in line with existing works except lamba parameters in loss function


Possible explorations/Open Questions:
Multiple benchmakrs
anchor selection methods inline with YOLOv2 using KMeans

Things learnt:
Loss function
Generic convdet
Covdet with skip connections
Anchor box optimization


