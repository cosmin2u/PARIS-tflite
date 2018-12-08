# PARIS-tflite

in folderul Ph2 ->

Pornire Tensorboard (in background): 
Windows > START /B tensorboard --logdir tf_files/training_summaries
Linux > tensorboard --logdir tf_files/training_summaries &

Re-antrenare:

python -m tesnorflow-for-poets-2.scripts.retrain --bottleneck_dir=tf_files/bottlenecks --how_many_training_steps=1000 --model_dir=tf_files/models/ --summaries_dir=tf_files/training_summaries/PARIS --output_graph=tf_files/retrained_graph_paris.pb --output_labels=tf_files/retrained_labels_paris.txt --architecture=""mobilenet_0.50_224"" --image_dir=tf_files/train

Clasificare:

python -m tensorflow-for-poets-2.scripts.label_image --graph=tf_files/retrained_graph_paris.pb --image=tf_files/train/tour_img-659439-148.jpg --labels=tf_files/retrained_labels_paris.txt
