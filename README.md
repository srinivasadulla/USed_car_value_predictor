# Used Car Value Prediction App

## Description

This project predicts the **resale value** of a car based on five user inputs and also provides a **deep learning-based image classification** system to predict the **make, model, and year** of a car from an uploaded image.

The application has three components:

- **ML Model (Backend)** – Predicts car value from structured inputs.
- **DL Model (Optional CLI Tool)** – Classifies car images.
- **Frontend (Flask Web Interface)** – Provides a user-friendly form for prediction.

---



## Execution

### ML Model (Backend)

- Run the training notebook to generate a car price prediction model.
- Export the trained model using `pickle` (e.g., `model.pkl`).
- Ensure the `.predict()` function accepts the same features provided by the frontend.

---

### Frontend (Flask Web App)

1. Open `app.py`.
2. Update **line 20** to point to your pickled model file (e.g., `'model.pkl'`).
3. Launch the Flask application:

   ```bash
   python3 app.py


### 🤖 Deep Learning Model (Car Image Classification)

#### 📁 Dataset Creation

Edit configuration values in `./config/cars_config.py` if needed.

Run the following scripts:

```bash
python download_images.py     # Download images using car_image_links.csv
python data_cleaning.py       # Clean and organize image data
python create_dataset.py      # Filter and format datasets per class
python build_dataset.py       # Split into train/test/val and encode labels



#### MXNet Record File Generation

Run the following commands in your **Linux terminal** to generate `.rec` files:

```bash
~/mxnet/bin/im2rec ./lists/train.lst "" ./rec/train.rec resize=256 encoding='.jpg' quality=100
~/mxnet/bin/im2rec ./lists/val.lst "" ./rec/val.rec resize=256 encoding='.jpg' quality=100
~/mxnet/bin/im2rec ./lists/test.lst "" ./rec/test.rec resize=256 encoding='.jpg' quality=100


#### Train the Model

Use the **VGG16** architecture by running:

```bash
python fine_tune_cars.py



#### Test the Model

Use the **VGG16** architecture by running:

```bash
python test_model.py
