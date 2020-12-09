### Integration of Custom Object Detection Model(Car Detection) in Mediapipe

For Installing & building Mediapipe on your machine **please follow the official [Mediapipe](https://github.com/google/mediapipe) repo** & this [blog](https://google.github.io/mediapipe/getting_started/install.html) by Google.

After Installing all the dependencies you should be able to run the Hello World example.

#### This Repo is mainly for integrating My Custom Car Detection Model with Mediapipe

I have trained My own Car Detection model from scratch using Tensorflow Object Detection [API](https://github.com/tensorflow/models), & converted into Tensorflow Lite, Mediapipe works with Tensorflow Lite Models.

You can build my Car Detection on Desktop using this command:

```shell
bazel build -c opt --define MEDIAPIPE_DISABLE_GPU=1 mediapipe/examples/desktop/car_detection:car_detection_tflite
```

To run the application, replace `<input video path>` and `<output video path>` in the command below with your own paths:

```shell
GLOG_logtostderr=1 bazel-bin/mediapipe/examples/desktop/car_detection/car_detection_tflite \
  --calculator_graph_config_file=mediapipe/graphs/car_detection/car_detection.pbtxt \
  --input_side_packets=input_video_path=<input video path>,output_video_path=<output video path>
```

You can find the sample video & output in this [folder](mediapipe/examples/desktop/car_detection)



