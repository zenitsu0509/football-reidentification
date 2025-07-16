# Football Player Re-identification and Tracking

This project implements a football player re-identification and tracking system using YOLOv8 and ByteTrack. The system can track multiple players in football video footage, maintaining consistent identities across frames.

## Features

- **Player Detection**: Uses YOLOv8 model for accurate player detection
- **Player Tracking**: Implements ByteTrack for consistent player tracking across frames
- **Re-identification**: Maintains player identities even when they temporarily leave the frame
- **Video Processing**: Processes entire video files and generates annotated output videos
- **Google Colab Support**: Optimized for running in Google Colab environment

## Project Structure

```text
football-reidentification/
├── README.md                          # This file
├── scoccer_reidentification.ipynb     # Main Jupyter notebook                       # Pre-trained YOLOv8 model (download separately)
└── video/
    ├── input              
    ├── output       
```

## Model Download

The trained model file (`best.pt`) is not included in this repository due to size constraints. Please download it from Google Drive:

**Download Link**: [best.pt model](https://drive.google.com/file/d/1-5fOSHOSB9UXyP_enOoZNAMScrePVcMD/view)

After downloading:

1. Create a `model` folder in the project directory if it doesn't exist
2. Place the `best.pt` file in the `model/` folder
3. The file structure should look like: `football-reidentification/model/best.pt`

## Requirements

- Python 3.7+
- OpenCV
- Ultralytics YOLOv8
- Google Colab (for cloud execution)

## How to Use in Google Colab

### Method 1: Upload Files to Google Drive

1. **Download the model file**:
   - Download `best.pt` from [this Google Drive link](https://drive.google.com/file/d/1-5fOSHOSB9UXyP_enOoZNAMScrePVcMD/view)
   - Place it in the `model/` folder

2. **Upload the repository to Google Drive**:
   - Upload the entire `football-reidentification` folder to your Google Drive
   - Note the path where you uploaded it (e.g., `/content/drive/MyDrive/football-reidentification/`)

3. **Open Google Colab**:
   - Go to [Google Colab](https://colab.research.google.com/)
   - Upload the `scoccer_reidentification.ipynb` notebook

4. **Run the notebook**:
   - Execute each cell in order
   - The notebook will automatically:
     - Mount your Google Drive
     - Install required packages
     - Load the model and process the video

### Method 2: Clone from GitHub

1. **Clone the repository in Colab**:

   ```python
   !git clone https://github.com/zenitsu0509/football-reidentification.git
   %cd football-reidentification
   ```

2. **Download the model file**:
   - Download `best.pt` from [this Google Drive link](https://drive.google.com/file/d/1-5fOSHOSB9UXyP_enOoZNAMScrePVcMD/view)
   - Upload it to Colab or your Google Drive
   - Place it in the `model/` folder

3. **Install dependencies**:

   ```python
   !pip install ultralytics opencv-python -q
   ```

4. **Run the tracking**:

   ```python
   import cv2
   from ultralytics import YOLO
   from google.colab.patches import cv2_imshow
   
   # Load model and process video
   model = YOLO('model/best.pt')
   # Follow the notebook cells for complete implementation
   ```

### Method 3: Step-by-Step Setup

1. **Download the model file**:
   - Download `best.pt` from [this Google Drive link](https://drive.google.com/file/d/1-5fOSHOSB9UXyP_enOoZNAMScrePVcMD/view)
   - Upload it to your Google Drive in the appropriate folder

2. **Mount Google Drive**:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

3. **Install required packages**:

   ```python
   !pip install ultralytics opencv-python -q
   ```

4. **Import libraries**:

   ```python
   import cv2
   from ultralytics import YOLO
   from google.colab.patches import cv2_imshow
   ```

5. **Set file paths** (adjust according to your Drive structure):

   ```python
   MODEL_PATH = "/content/drive/MyDrive/football-reidentification/model/best.pt"
   VIDEO_PATH = "/content/drive/MyDrive/football-reidentification/video/football.mp4"
   OUTPUT_VIDEO_PATH = "/content/drive/MyDrive/football-reidentification/video/football_output.mp4"
   ```

6. **Load the model**:

   ```python
   model = YOLO(MODEL_PATH)
   ```

7. **Process the video**:
   - The notebook contains the complete video processing code
   - It will track players and save an annotated output video

## Model Information

The `best.pt` model is a custom-trained YOLOv8 model specifically fine-tuned for football player detection and tracking. It includes:

- Player detection capabilities
- Team differentiation
- Optimized for football field environments

## Output

The system generates:

- **Annotated video**: Shows bounding boxes around detected players
- **Tracking IDs**: Consistent player identification across frames
- **Frame-by-frame display**: Shows sample frames during processing

## Performance

- **Processing Speed**: Depends on video resolution and length
- **Accuracy**: High accuracy for player detection and tracking
- **Memory Usage**: Optimized for Google Colab's memory constraints

## Troubleshooting

### Common Issues

1. **File not found error**:
   - Ensure all files are uploaded to the correct Google Drive path
   - Check that the file paths in the notebook match your Drive structure
   - **Important**: Make sure you've downloaded the `best.pt` model file from the Google Drive link

2. **Model loading issues**:
   - Ensure the `best.pt` model file is downloaded from [this Google Drive link](https://drive.google.com/file/d/1-5fOSHOSB9UXyP_enOoZNAMScrePVcMD/view)
   - Verify the model file is in the correct location: `model/best.pt`
   - Check that the model file is not corrupted during download

3. **Memory issues**:
   - Use smaller video files for testing
   - Reduce video resolution if needed

### Tips for Better Performance

1. **Use GPU runtime**:
   - In Colab: Runtime → Change runtime type → GPU

2. **Optimize video settings**:
   - Use compressed video formats (MP4 with H.264)
   - Consider reducing frame rate for faster processing

3. **Monitor resources**:
   - Check RAM usage in Colab
   - Clear variables when not needed

## Contributing

Feel free to contribute to this project by:

- Improving the tracking algorithm
- Adding new features
- Optimizing performance
- Fixing bugs

## License

This project is open source and available under the MIT License.

## Author

Created by zenitsu0509

---

**Note**: This project is designed to work seamlessly with Google Colab. Make sure you have sufficient storage space in your Google Drive and a stable internet connection for the best experience.
