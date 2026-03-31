# AI Usage Log
# AI Usage Log

## Project
Motion Deblurring and Object Detection Pipeline

## Purpose
This log records how AI assistance was used during the development of the assignment repository, including code generation, refactoring, modularization, documentation, and Git workflow planning.

---

## Entry 1
**Date:** 2026-03-31  
**Tool:** ChatGPT  
**Task:** Repository planning and pipeline structuring  
**AI Output Summary:** Produced a full end-to-end pipeline with task flow covering:
- project setup
- dataset download and extraction
- paired blur/sharp image collection
- deblurring and PSNR/SSIM evaluation
- detection analysis on blurred/deblurred/sharp images
- pseudo-label generation
- training dataset preparation
- detector training
- evaluation across three domains  
**How It Was Used:** Used as the initial implementation blueprint for the project pipeline.  
**Verification Performed:** Code structure and sequencing were checked manually against assignment requirements.  
**Notes:** Final code was later separated into task-wise files for cleaner execution and Git commit history.

---

## Entry 2
**Date:** 2026-03-31  
**Tool:** ChatGPT  
**Task:** Task-wise code modularization   
**AI Output Summary:** Refactored the pipeline into task-wise modules:
- `task1_setup.py`
- `task2_deblurring.py`
- `task3_detection.py`
- `task4_training.py`
- `task5_evaluation.py`
- `run_tasks.py`  
**How It Was Used:** Adopted to make each assignment task runnable independently.  
**Verification Performed:** Reviewed function boundaries and confirmed that outputs from one task could be passed to the next task.  
**Notes:** This improved reproducibility and made commit history easier to organize.

---

## Entry 3
**Date:** 2026-03-31  
**Tool:** ChatGPT  
**Task:** Deblurring implementation support  
**AI Output Summary:** Generated classical image restoration code using motion PSF and Wiener deblurring, plus PSNR/SSIM evaluation and qualitative visualization.  
**How It Was Used:** Integrated into Task 2 for restoration experiments on blurred image pairs.  
**Verification Performed:** Output images, PSNR, and SSIM values were checked on sample images.  
**Notes:** Method choice was documented as a classical baseline.

---

## Entry 4
**Date:** 2026-03-31  
**Tool:** ChatGPT  
**Task:** Object detection analysis support  
**Prompt Summary:** Asked for pretrained YOLO inference on blurred, deblurred, and sharp images.  
**AI Output Summary:** Generated detection inference code to compare:
- number of detections
- confidence scores
- runtime/latency
- saved detection visualizations  
**How It Was Used:** Integrated into Task 3 to study the effect of image restoration on visual understanding.  
**Verification Performed:** Detection outputs were visually inspected and comparison CSV files were generated.  
**Notes:** Inference was used before training to analyze restoration impact.

---

## Entry 5
**Date:** 2026-03-31  
**Tool:** ChatGPT  
**Task:** Pseudo-label generation for missing detection annotations  
**AI Output Summary:** Suggested generating pseudo-labels from sharp images using a pretrained detector, then remapping classes and using them for training/evaluation.  
**How It Was Used:** Applied as a practical workaround to enable full pipeline completion.  
**Verification Performed:** Checked whether label files were created and whether class names were extracted successfully.  
**Notes:** This limitation was clearly documented in README/report because pseudo-labels are noisier than human annotations.

---

## Entry 6
**Date:** 2026-03-31  
**Tool:** ChatGPT  
**Task:** Training and evaluation pipeline  
**AI Output Summary:** Generated code to:
- stratify images by blur level
- split train/val/test sets
- create restored-image YOLO dataset
- fine-tune YOLO
- evaluate trained weights on three domains
- save summary metrics and plots  
**How It Was Used:** Used directly in Task 4 and Task 5 implementation.  
**Verification Performed:** Training outputs, saved weights, evaluation summaries, and plots were manually checked.  
**Notes:** Large generated files were excluded from GitHub using `.gitignore`.

---

## Entry 7
**Date:** 2026-03-31  
**Tool:** ChatGPT  
**Task:** Git workflow and commit planning   
**AI Output Summary:** Produced task-wise commit strategy aligned with project milestones:
- setup/documentation
- deblurring
- detection analysis
- training preparation
- evaluation  
**How It Was Used:** Used to create a clean and descriptive Git commit history.  
**Verification Performed:** Commit messages were reviewed and matched to repository changes.  
**Notes:** Atomic commits were preferred over one large commit.

---

## Ethical Reflection
AI assistance was used for code drafting, refactoring, documentation, and workflow planning.  
All AI-generated code was reviewed, adapted, and tested before use.  
No AI output was accepted blindly without checking execution behavior and assignment relevance.

## Licensing Reflection
The project uses external resources such as:
- Kaggle-hosted GoPro deblur dataset
- Ultralytics YOLO pretrained models

These dependencies should be acknowledged in the report, and their licenses should be checked before redistribution.

## Bias / Reliability Reflection
The generated training labels are pseudo-labels, not manually verified annotations.  
This introduces possible bias and label noise, which may affect:
- training quality
- evaluation reliability
- class distribution validity

This limitation should be explicitly stated in the report.

## Verification Summary
The following forms of checking were performed:
- code execution in Colab
- manual inspection of output folders
- visual inspection of restored and detected images
- metric file review (`PSNR`, `SSIM`, confidence, mAP-related outputs)
- Git status and repository structure checks
