---
license: cc-by-4.0
---

original dataset link:
https://huggingface.co/datasets/jchen396/cao_cautery/tree/main

# Dataset and Imitation Learning Framework for Autonomous Tumor Resection

We present **cao_cautery**, the first long-horizon dataset for autonomous tumor resection on the **da Vinci Research Kit (dVRK)**. This dataset captures a challenging dual-arm resection workflow where one arm retracts tissue while the other performs electrocautery-based cutting. It is designed to support research in robotic surgery, imitation learning, and visual policy learning under realistic intraoperative conditions.

---

## Dataset Summary

- **3,640+ dual-arm demonstrations** of resection tasks
- Recorded on anatomically constrained **phantom tumors**
- Each demonstration segmented into **structured subtasks**
- Includes **multi-view video** and **synchronized robot kinematics**
- Demonstrations reflect realistic intraoperative challenges:
  - **Soft-tissue deformation**
  - **Smoke-induced occlusion**
  - **Shifting illumination and camera perspectives**

The dataset supports imitation learning, vision-language-action modeling, and multi-view surgical policy training under varying data regimes.

---

## File Structure

Each demonstration episode is stored under:

cao_cautery/
tissue_<id>/
1_resection/ # Task
<timestamp>/
left_img_dir/ # Left endoscope images
right_img_dir/ # Right endoscope images
endo_psm1/ # Wrist camera (right arm)
endo_psm2/ # Wrist camera (left arm)
ee_csv.csv # Kinematics log


- Images are in `.jpg` format
- `ee_csv.csv` contains timestamped poses, joint angles, jaw positions, and control targets for PSM1, PSM2, ECM, and SUJ arms

---

## Applications

This dataset is designed for:
- Visual imitation learning and offline reinforcement learning
- Learning dual-arm coordination and tool-tissue interaction
- Studying robustness under partial occlusion and dynamic visual changes
- Subtask-conditioned policy learning and benchmarking

---

## Format

- RGB image resolution: varies (synchronized across views)
- Kinematics format: CSV with ~100 columns
  - End-effector position/orientation
  - Joint states and commands
  - Jaw and RCM pose
  - PSM1, PSM2, ECM, SUJ poses
- Data regimes supported for training:
  - Full dataset
  - 60% subset
  - 3% few-shot subset

---

## Citation

If you use this dataset, please cite:

```bibtex
@misc{cao2025,
  title       = {Dataset and Imitation Learning Framework for Autonomous Tumor Resection},
  author      = {Nural Yilmaz, Juo-Tung Chen, Mariana Smith, Ji Woong Kim, Brendan Burkhart, Axel Krieger},
  year        = {2025},
  note        = {Under review},
  howpublished = {\url{https://huggingface.co/datasets/jchen396/cao_cautery}}
}
```
## License
This dataset is licensed under CC-BY-4.0. Please credit the authors when using this dataset.

## Contact
For questions or collaboration inquiries, please contact:

Juo-Tung Chen
jchen396@jh.edu
Johns Hopkins University
