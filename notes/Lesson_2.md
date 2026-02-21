# Four Decades of OCR Evoulution

## Agenda

- [Tesseract](#tesseract-ocr-1980s---2010s)
  - Traditional OCR Model
- [PaddleOCR](#paddleocr-and-deep-learning-era-late-2010s---present)
  - Modern OCR Model
- Application & Limitations
  - Comparison of Models

## OCR Eras

- Evolution of Document Intelligence<sup>[1](#ref-doc_intelligence_evolution)</sup>
  ![Evolution of document intelligence](../images/2_0.png)
- Tesseract
  - Stands for the traditional, procedural Computer Vision approach
  - Lots of hand engineering, steps, rules
- PaddleOCR
  - Representative of the Deep Learning era
  - Uses neural network end-to-end for detection and recognition
- Shift from Tesseract style to PaddleOCR style systems
  - Mirrors the broader shift in AI
  - Carefully designed pipelines with handcrafted features &rarr; Data-driven trainable models that learn directly from examples

## Tesseract OCR (1980s - 2010s)

- Tesseract follows the **traditional approach**.
  - Relies on a rigid sequence of steps
    - Line finding
    - Word recognition
    - Character classification
- **Pros**
  - Extensive support for **100+ languages**.
  - Works well for clean, high-resolution printed documents.
  - Lightweight CPU-only
    - Deployable on resource-contrained systems.
- **Limitations**
  - Struggles with "text-in-the-wild" scenarios
    - Cannot reliably interpret handwriting or low-quality scans.
    - Performs poorly on complex or irregular layouts
      - Curved text
      - Multi-column documents
      - Noisy backgrounds
- Releases<sup>[2](#ref-Tesseract_releases)</sup>

### Tutorials & Publications

- Publication: An overview of Tesseract OCR Engine<sup>[3](#ref-overview_Tesseract_OCR_Engine)</sup>
- Tutorial slide deck by Ray Smith at Document Analysis Systems (2016)<sup>[4](#ref-Tesseract_tutorial_DAS_2016)</sup>
  ![tutorial contents](../images/2_1.png)

## PaddleOCR and Deep Learning Era (Late 2010s - Present)

- Circa 2015, two-stage pipeline using deep learning becomes new OCR standard
  - **Text Detection Model**
    - Find the regions that contain text
  - **Text Recognition Model**
    - Read the content of each text region

- PaddleOCR<sup>[5](#ref-PaddleOCR_Technical_Report)</sup>
  - Developed by Baidu in 2020
  - Open-source deep learning OCR system
  - Components and algorithms
    - **Text Detection Model**
      - DBNet (Differentiable Binarization Network)
    - **Text Recognition Model**
      - SVTR (current)
      - SRN (former)
      - CRNN (earliest)
  - Pros
    - Reasonably **accurate** on complex, irregular and curved text.
    - More **efficient** when accelerated by GPUs
    - Offers lighter weight options designed for deployment on **mobile and edge** devices.

- Tesseract vs PaddleOCR
  ![Tesseract vs PaddleOCR](../images/2_2.png)

## References

<span id="ref-doc_intelligence_evolution">1.</span> [Evolution of Document Intelligence](https://landing.ai/blog/ocr-to-agentic-document-extraction-a-look-into-the-evolution-of-document-intelligence)  
<span id="ref-Tesseract_releases">2.</span> [Tesseract Releases](https://tesseract-ocr.github.io/tessdoc/ReleaseNotes.html)  
<span id="ref-overview_Tesseract_OCR_Engine">3.</span> [An Overview of the Tesseract OCR Engine by Ray Smith (2017)](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/33418.pdf)  
<span id="ref-Tesseract_tutorial_DAS_2016">4.</span> [Tesseract tutorial at DAS 2016](https://tesseract-ocr.github.io/docs/)  
<span id="ref-PaddleOCR_Technical_Report">5.</span> [PaddleOCR 3.0 Technical Report](https://arxiv.org/pdf/2507.05595)  
