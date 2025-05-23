**Medical Bone Segmentation & Landmark Detection**
Automated CT knee scan analysis for surgical planning and medical research
**What This Does**
Automatically identifies and analyzes femur and tibia bones from CT scans, creating precise bone boundaries and finding key anatomical landmarks that doctors need for surgeries and treatments. What takes hours manually now happens in minutes with consistent accuracy.

**How It Works**

1. Bone Segmentation
   Separates femur and tibia from CT scans using bone density thresholds and anatomical knowledge.

Uses 300 HU threshold for cortical bone detection
Applies morphological cleaning to remove noise
Multiple fallback strategies ensure reliability across different scan qualities

2. Boundary Expansion
   Creates multiple mask versions for different clinical needs.

Uniform expansion: Perfect 2-4mm safety margins around bones
Randomized boundaries: Natural-looking irregular borders mimicking biological variation
Original masks: Exact bone boundaries from scans

3. Landmark Detection
   Automatically locates key anatomical reference points on bone surfaces.

Identifies medial and lateral tibia landmarks
Converts coordinates to real-world millimeter measurements
Compares landmark positions across different boundary definitions

**Technical Approach**
Core Technologies: Python with medical imaging libraries (nibabel, scipy, numpy)
Methods: Classical computer vision - no black-box AI, fully interpretable results
Key Algorithms:

Intensity-based thresholding using Hounsfield Units
Morphological operations for noise reduction and gap filling
Connected component analysis for bone separation
Distance transform-based expansion with randomization
Surface extraction using erosion-based methods
