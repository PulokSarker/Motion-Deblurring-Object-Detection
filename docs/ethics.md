# Ethics, Licensing, and Bias Notes
# Ethics, Licensing, and Bias Considerations

## 1. Introduction
This project explores the relationship between image restoration (motion deblurring) and visual understanding (object detection). As the system integrates multiple datasets, pretrained models, and AI-assisted development, it is important to consider ethical, legal, and technical implications.

---

## 2. Ethical Considerations

### 2.1 Responsible Use of AI
AI tools (e.g., ChatGPT) were used to assist in:
- code generation
- debugging
- modular design
- documentation writing

All AI-generated outputs were:
- reviewed manually
- tested in Colab
- modified when necessary

No AI output was used blindly without verification.

---

### 2.2 Transparency and Attribution
All AI-assisted contributions have been:
- documented in the AI usage log (`logs/ai_logs/ai_usage_log.md`)
- clearly separated from manually written code where applicable

This ensures transparency in development and aligns with academic integrity requirements.

---

### 2.3 Reproducibility
The project is designed to be reproducible by:
- downloading datasets programmatically (Kaggle API)
- using fixed random seeds
- providing modular task-wise scripts

---

## 3. Licensing Considerations

### 3.1 Dataset License
The project uses the **GoPro Deblur Dataset** (via Kaggle):
- Dataset ownership belongs to original creators
- Used only for academic and research purposes
- Not redistributed in the repository

To comply with licensing:
- dataset is downloaded programmatically
- dataset files are excluded from GitHub using `.gitignore`

---

### 3.2 Pretrained Models
The project uses pretrained YOLO models (Ultralytics):
- These models follow their respective licenses
- Used only for inference and fine-tuning in this project

---

### 3.3 Code Licensing
All code in this repository is:
- intended for academic use
- structured and documented for reproducibility

If reused, proper citation should be given.

---

## 4. Data Privacy and Security

- No personal or sensitive data is used in this project
- All images are from public datasets
- No user-identifiable information is processed

---

## 5. Bias and Limitations

### 5.1 Dataset Bias
The GoPro dataset:
- focuses on specific motion blur patterns
- may not represent all real-world scenarios

This can affect generalization of the trained model.

---

### 5.2 Pseudo-label Bias
Since the dataset does not contain object detection labels:
- pseudo-labels were generated using a pretrained model

Limitations:
- labels may be noisy or incorrect
- errors from the pretrained model propagate into training

---

### 5.3 Model Bias
The pretrained YOLO model:
- is trained on general datasets (e.g., COCO)
- may not perform equally well across all object categories

---

### 5.4 Restoration Artifacts
Deblurring methods may:
- introduce artifacts
- distort object boundaries

This can negatively affect detection accuracy.

---

## 6. Limitations of the Approach

- Classical deblurring (Wiener filter) may not fully restore complex motion blur
- Pseudo-labels are not a substitute for human-annotated ground truth
- Training dataset size is limited due to computational constraints
- Performance depends heavily on preprocessing quality

---

## 7. Future Improvements

- Use deep learning-based deblurring models (e.g., DeblurGAN, MPRNet)
- Replace pseudo-labels with manually annotated bounding boxes
- Use larger and more diverse datasets
- Apply domain adaptation techniques
- Improve evaluation with per-class analysis and error categorization

---

## 8. Conclusion

This project demonstrates a full pipeline integrating image restoration and object detection. While AI tools and pretrained models accelerate development, careful consideration of ethics, licensing, and bias is essential to ensure responsible and reliable outcomes.

All limitations and assumptions have been documented to support transparency and reproducibility.
