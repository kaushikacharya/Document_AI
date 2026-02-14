# Introduction

## Course Orientation

- This course teaches building **document processing pipeline** that transform complex documents `->` LLM-ready markdown text and extract information for analysis.
- Start with traditional OCR
  - Extract only text
- Then add techniques to
  - Detect document structure and
  - Identify visual components like
    - Tables with complex formatting like merged cells
    - Charts with captions
    - Forms with checkboxes
- Implement **agentic workflow** that combines layout detection with LLM-based reasoning.
- Then learn to use Landing AI's Agentic Document Extraction (ADE), which automates the above mentioned entire workflow.
  - Build a pipeline using ADE to parse mixed documents and extract required key-value pairs.
- Integrate ADE extraction information into RAG applications.
- Implement a cloud-based version on AWS using an event-driven architecture that automatically triggers ADE for document processing whenever new documents appear.

## Traditional OCR limits

- Traditional OCR systems work by segmenting documents into individual characters and then classifying each character using supervised learning.
- Even though they can extract characters with high accuracy, but they lack how different parts of a document hang together, such as
  - tables
  - forms
  - reading order of different elements of a document

## Landing AI's ADE capability

- ADE treats documents as visual objects
  - Simplified explanation
    - Treats each page of a document as an image
    - Breaks down the image into parts
    - Then extracts from each part separately using an agentic workflow.

  - Technical explanation
    - Visual objects encoded in **layout structure** and **spatial relationships**
    - Uses **custom visual models** that directly interprets
      - Complex tables
      - Graphs
      - Images
      - Charts
      - and other elements
    - Grounds every extracted piece of text to a precise location on the page.

- ADE uses an agentic orchestration layer that decomposes complex documents into smaller sections for careful examination in several steps.

- Analogy with human's approach to processing document
  - Humans don't process document with a single glance
  - Instead, we examine the different parts of the document to pull out information piece by piece in multiple iterations.
  - ADE might extract the table and then further extract the table structure: identifying rows, columns, merged cells, and so on.
