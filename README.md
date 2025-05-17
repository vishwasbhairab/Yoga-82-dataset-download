
# Yoga Pose Image Dataset (Yoga-82)

This repository/documentation explains how the **Yoga-82** dataset was downloaded and organized for pose detection and classification tasks using Deep Learning.

## 📁 Dataset Description

**Yoga-82** is a dataset containing 82 classes of yoga poses. Each pose is stored in a `.txt` file which includes:
- The relative image path and image filename
- A direct link to download the image

There are also split files:
- `yoga_train.txt` and `yoga_test.txt` provide the split for training and testing datasets.
- Each line in these split files follows the format:
  ```
  <image_path>,<label_for_class_6>,<label_for_class_20>,<label_for_class_82>
  ```

## 📥 How the Dataset Was Downloaded

1. **Downloaded `.txt` Files:**  
   All `.txt` files were accessed from the official Yoga-82 dataset folder. These include both class-specific files and train-test splits.

2. **Parsed and Extracted URLs:**  
   Each class file was read, and the image paths and corresponding download URLs were extracted line by line.

3. **Downloaded Images Using `requests`:**  
   Images were downloaded using the `requests` library (instead of `wget`) for better cross-platform compatibility and error handling.

4. **Saved Images to Folders:**  
   - Created a folder structure like: `Images/<pose_class>/image.jpg`
   - Verified each image using `PIL.Image` to detect and discard corrupted files.

5. **Resumed Downloads if Interrupted:**  
   The script checks whether a file already exists to prevent downloading the same image again after a kernel restart.

## 🧾 Credit

The dataset was originally published on **Google Sites** by the authors of Yoga-82:

🔗 **[Yoga-82 Dataset (Google Sites)](https://sites.google.com/view/yoga-82/home)**

Please cite their work or refer to their publication if you use the dataset in your project or research.

## 🔧 Tools Used

- Python
- `requests`, `os`, `tqdm`, `PIL`
- Jupyter Notebook / Google Colab

## 📌 Note

This dataset is intended for research and educational use. Ensure to comply with the dataset license and terms from the original authors.
