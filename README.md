# tfserving-web-demo

A web example project to demo how to call TF Serving from a website

## Usage

1. Download the Inception v3 SavedModel from [TFHub](https://tfhub.dev/google/imagenet/inception_v3/classification/5)
2. Start TF Serving with:
`docker run -t --rm -p 8501:8501     -v "/path/to/inception_v3/SavedModel/folder:/models/inception_v3"     -e MODEL_NAME=inception_v3     tensorflow/serving`
3. If you are not running TF Serving on your local machine, by default many browser will block cross-origin request. So you need to disable CORS policy. For Chrome on Mac, this is the way to do it (only for development testing):
`open -n -a /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --args --user-data-dir="/tmp/chrome_dev_test" --disable-web-security`

If you are not running TF Serving on your local machine, replace 'localhost' with your TF Serving host's IP address. You do not need to worry about CORS. 

4. Load tfserving-demo.html by directly using a brower or use a simple HTTP server

test image is from: https://github.com/tensorflow/models/tree/master/research/object_detection/test_images/
