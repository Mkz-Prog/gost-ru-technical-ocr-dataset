---
license: mit
language:
- ru
---
# Dataset Card for Dataset Name

<!-- Provide a quick summary of the dataset. -->

Synthetic OCR dataset of Russian technical drawings text generated with [TextRecognitionDataGenerator](https://github.com/Belval/TextRecognitionDataGenerator).

## Dataset Details

### Dataset Description

<!-- Provide a longer summary of what this dataset is. -->

Texts include engineering terms, GOST standards, dimensions, specifications, and full Cyrillic alphabet coverage.

## Uses

<!-- Address questions around how the dataset is intended to be used. -->

This synthetic OCR dataset is specifically designed for training and evaluating text recognition models on technical documentation, with a strong focus on Russian language and the unique characteristics of GOST-standardized documents. 

### Direct Use 

Training OCR Models: Ideal for developing robust OCR systems capable of accurately reading complex technical drawings, blueprints, and engineering specifications.
Language & Font Specificity: Perfectly suited for models that need to handle Russian text (Cyrillic) and the distinctive GOST font, which is commonly used in industrial and construction documentation.
Real-World Scenario Simulation: The dataset includes realistic variations such as:
- Mixed alphanumeric strings (10500.31230.123СБ, 1:10)
- Complex symbols and punctuation (70x5=350, п.7 TT)
     
Benchmarking: Useful for comparing the performance of different OCR algorithms when processing technical content.
     

### Advanced Use Cases 

Building Specialized Datasets: Can serve as a foundation for creating larger, more diverse datasets by combining it with real-world data.
Model Robustness Testing: The controlled generation process allows for systematic testing of how well a model handles specific distortions (skew, blur, noise).
Research in Document Analysis: Provides a standardized resource for research into automated document processing, particularly in engineering and manufacturing domains.

## Dataset Structure 

The dataset is organized into two main components: 
1. Images (images/) 

Total Count: 1,000 images.
File Formats: A mix of JPEG and PNG formats to simulate real-world document storage and exchange scenarios.
Image Size: Automatically resized to a standard resolution of approximately 640x480 pixels (with minor variations).
Content: Each image contains one or more lines of text generated using the GOST.TTF font. The text represents realistic engineering and technical documentation, including:
- Part numbers and codes (e.g., 10500.31230.123СБ)
- Technical terms (e.g., "Каркас площадки", "Сборочный чертеж")
- Measurements and scales (e.g., 16,0, 1:10, 70x5=350)
- Special symbols and punctuation (e.g., п.7 TT, * Размеры для справок.)
     
Visual Properties: Images are synthetically generated with controlled variations to enhance realism:
- Background: Gaussian noise resembling a light white background.
- Distortions: Subtle random skewing (up to 5°), minimal sinusoidal distortion, and slight random blurring.
- Alignment: Text is centered horizontally.
         
     

2. Labels (labels.csv) 

Format: A plain CSV file with comma as the delimiter.
Structure:
- filename: A string representing the name of the corresponding image file (e.g., image_0001.jpg).
- words: A string containing the complete text found on that image, preserving all original characters, spaces, and punctuation (e.g., "10500.31230.123СБ").