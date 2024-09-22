## Directory Structure

```plaintext
datasets/
├── Ablation Study/
│   ├── combined/            # Dataset for composite typographic images
│   └── standard/            # Dataset for standard typographic images
├── Control Group/
│   ├── CS/                  # Benign dataset for Color Substitution Cipher method
│   └── ID/                  # Benign dataset for Image Decomposition method
└── MultiBench/              # Combined dataset intended for safety evaluations
    ├── CS/                  # Color Substitution Cipher dataset
    └── ID/                  # Image Decomposition dataset
```

## Dataset Structure

Each entry in the dataset has the following keys:

- **ID**: A unique identifier for the dataset entry.
- **Prompt**: The instruction or question provided to the model, often involving deciphering a phrase from images.
- **Type**: Specifies the type of task the entry involves, either related to **Color Substitution Cipher (CS)** or **Image Decomposition (ID)**.
- **Category**: High-level category of the task (e.g., "Privacy").
- **Subcategory**: More specific categorization within the main category (e.g., "Privacy").
- **Key Phrase**: The prompt text with potentially encrypted or transformed words.
- **Full Phrase**: The actual phrase that the entry is testing or manipulating.
- **Images**: A list of file paths for images used in the task. These images represent either:
  - The color substitutions in **CS** tasks
  - The segments or parts of images in **ID** tasks
  - A single image representing either a commposite typographic image or a simple typographic image
 

## Accessing the Dataset

You can easily load any dataset from a JSON file with Python for example. Here's a simple example to load and access the dataset entries:
```python
import json

with open('multibench.json', 'r') as file:
    dataset = json.load(file)
```
