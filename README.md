# YOLOv10 Object Detection

Run YOLOv10 ONNX object detection on an image, video, or webcam using OpenCV and ONNX Runtime.

## Setup

Use Python 3.10 or later, then install the dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

The pretrained `yolov10n.onnx` model is intentionally not included. Obtain or export a compatible YOLOv10 ONNX model and pass its path with `--model`. The model should accept 640-by-640 images and return detections in `[x1, y1, x2, y2, confidence, class_id]` format.

## Run

Run the bundled sample video:

```powershell
python detection.py --source data/videos/road.mp4 --model path\to\yolov10n.onnx
```

Run an image or the default webcam instead:

```powershell
python detection.py --source data/images/zidane.jpg --model path\to\yolov10n.onnx
python detection.py --source 0 --model path\to\yolov10n.onnx
```

The script also accepts `--names` for a class-name file and `--tresh` for the confidence threshold (default `0.35`). Press `q` to close the display window.

## Included sample media

The sample images and video are included with the project owner's explicit authorization to redistribute. Original source-specific license details were not available when this repository was prepared; check upstream terms before reusing the media elsewhere.

## Model notice

Model weights are excluded from this repository. Ensure that the model you obtain is compatible with its source license and the intended use.
