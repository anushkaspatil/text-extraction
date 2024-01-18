# Text Extractor

## Goal
The purpose of this project is to process images and PDF files to extract text using the OpenCV approach and Pytesseract exclusively.

## User Story
As a user, I should be able to easily process images and extract text from them using this tool.

## Approach

### Try 1:
Text extraction is achieved using Pytesseract and Tesseract-OCR, with the pdf2image library converting PDFs into images for processing. The function to extract text from images directly utilizes the `image_to_string` method of Pytesseract. For PDFs, a combination of OpenCV and Tesseract is employed for image preprocessing and text extraction.

In Try 1, there was an issue with the second image. This limitation is addressed in Try 2.

### Try 2:
Try 2 focuses solely on text extraction but employs a different approach:
- The image is split into three color channels (red, green, blue), and the image is visualized using Matplotlib to provide the user with a preview of the uploaded image or specified image path.
- A configuration string is passed to Tesseract OCR when using the `image_to_string` function from `pytesseract`. The configuration includes parameters such as `-l eng` (language set to English), `--oem 3` (OCR Engine Mode set to LSTM), and `--psm 6` (Page Segmentation Mode set to sparse text with OSD).
- The extracted text is printed.

## Resources
1. [Tesseract Documentation](https://github.com/tesseract-ocr/tesseract)
2. [Medium Blog: How to Use Tesseract Library for OCR in Google Colab Notebook](https://bhadreshpsavani.medium.com/how-to-use-tesseract-library-for-ocr-in-google-colab-notebook-5da5470e4fe0)
3. [Blog: OCR with Tesseract](https://nanonets.com/blog/ocr-with-tesseract/)

## License
This project is licensed under the [MIT License](LICENSE).
