# SSDLiteCustom
Failed attempt at finetuning PyTorch's pretrained Mobilenet SSD with custom gIOU loss function

The model comes with its own .compute_loss() method which didn't react well with custom dataset, so attempted custom loss using generalised IOU (gIOU), results were worse as had to train model in eval() mode due to built-in changes to the forward pass of the model, leading to some layers not being trained properly.

If you found this while trying to fine tune pre-trained pytorch object detection models, you should call dir(model) to check if the model has build-in loss functions before attempting to create your own. 
