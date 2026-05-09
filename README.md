SSrename is a Python CLI tool that automatically renames screenshots using OCR-first text extraction with an AI-based fallback for images that lack sufficient readable text.

It is designed to work fully offline, using local models, and supports both directories and individual image files.

Features
OCR-first filename generation using EasyOCR
Automatic AI fallback using a local Vision-Language Model (BLIP)
Adaptive OCR thresholds based on screenshot type (code, chat, document, empty)
Works on both directories and single image paths
Safe preview mode with --dry-run
Collision-safe renaming
Customizable filename length
Multiple CLI flags for control and debugging
How It Works
For each image:

Extract text using EasyOCR
Detect screenshot type (code / chat / document / empty)
Check if OCR text meets the required word threshold
If insufficient → generate a caption using BLIP
Clean and rank keywords
Generate a meaningful filename
Preview or apply the rename safely
Installation
1. Clone the repository
git clone https://github.com/your-username/SSrename.git
cd SSrename
2. Create and activate a virtual environment
conda create -n ssrename python=3.11
conda activate ssrename
3. Install the package
pip install -e .
Usage
Rename all screenshots in a directory (dry run)
ssrename screenshots/ --dry-run
Rename a single image
ssrename path/to/image.png --dry-run
Limit processing to first N images
ssrename screenshots/ --limit 5 --dry-run
Show how names are generated
ssrename screenshots/ --verbose
OCR only (disable AI fallback)
ssrename screenshots/ --ocr-only
AI only (skip OCR)
ssrename screenshots/ --ai-only
Control filename length
ssrename screenshots/ --max-words 3
About
SS-rename is a Python CLI tool that automatically renames screenshots using OCR-first text extraction with an AI-based fallback

Topics
rename-image ssrename
Resources
 Readme
License
 MIT license
 Activity
Stars
 0 stars
Watchers
 1 watching
Forks
 0 forks
Report repository
Releases
No releases published
Packages
No packages published
Contributors
1
@merintheres
merintheres Merin Theres Jose
Languages
Python
100.0%
Footer
