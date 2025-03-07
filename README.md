# Image Captioning and Web Content Summarization

## Overview
This project extracts images and meaningful text from web pages, then processes the images using an AI-based captioning model and summarizes the text. The system is designed to handle different webpage structures, avoid irrelevant content, and ensure robustness against broken or invalid images.

## Features
- **Extract Images from Webpages**: Parses webpages and retrieves relevant images while filtering out icons, logos, and tracking pixels.
- **Extract Meaningful Text**: Removes navigation, footers, and advertisements to obtain clean textual content.
- **Image Captioning**: Uses an AI model to generate detailed descriptions of extracted images.
- **Multi-threaded Processing**: Efficient handling of multiple images using thread-based parallelism.
- **NSFW Content Detection**: Prevents processing of inappropriate websites based on URL keywords.
- **Error Handling**: Robust logging and exception handling for improved reliability.

## Technologies Used
- **Python**: Core scripting language
- **Requests**: Fetches web content
- **BeautifulSoup**: Parses HTML to extract text and images
- **Pillow (PIL)**: Handles image processing and validation
- **ThreadPoolExecutor**: Enables parallel processing of images
- **Gradio**: Provides a user interface

## Installation
### Prerequisites
Ensure you have Python 3.x installed along with the following dependencies:
```sh
pip install requests beautifulsoup4 pillow gradio
```

## Usage
### Running the Script
Run the script using:
```sh
python main.py
```

### Extracting Images
Call the function:
```python
images = extract_images_from_url("https://example.com")
```

### Extracting Text
Call the function:
```python
text = extract_text_from_url("https://example.com")
```

### Generating Image Captions
```python
caption = generate_caption(image_data)
```

## API Integration
This project interfaces with an AI model for captioning via:
```json
POST http://localhost:1234/v1/chat/completions
```

## Known Issues and Improvements
- **Handling Dynamic Content**: Pages rendered with JavaScript may not load images correctly.
- **Alternative Image Retrieval Methods**: Consider Selenium for dynamic content scraping.
- **Improved NSFW Detection**: Extend filtering beyond URL-based heuristics.

## License
MIT License

