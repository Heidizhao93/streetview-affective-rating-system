# Street-view Affective Rating System

A Jupyter Notebook interface for collecting multi-respondent affective ratings of street-view images. The system assigns a balanced image subset to each respondent, records seven Likert-scale ratings, supports interrupted-session recovery, and exports progress and completed responses.

## Features

- Balanced random image assignment across respondents
- Seven-item Likert-scale rating interface
- Automatic progress saving and session recovery
- CSV output for respondent-level results
- Excel summary of assignments and completion status
- Jupyter widget-based interface

## Repository contents

- `streetview_rating_system.ipynb`: executable rating interface
- `example_images/`: place input street-view images here
- `requirements.txt`: Python dependencies
- `CITATION.cff`: software citation metadata
- `LICENSE`: MIT License
- `UPLOAD_CHECKLIST.md`: checks to complete before making the repository public

## Requirements

- Python 3.10 or later
- JupyterLab or Jupyter Notebook

Install the dependencies:

```bash
python -m pip install -r requirements.txt
```

## Usage

1. Put the street-view images to be rated in `example_images/`. Supported formats are `.jpg`, `.jpeg`, and `.png`.
2. Open `streetview_rating_system.ipynb` in JupyterLab or Jupyter Notebook.
3. If needed, change `num_respondents` and `images_per_person` in the final cell.
4. Run the notebook cell and use the displayed interface.
5. Results are written to the `评分结果` subfolder inside the selected image folder.

The default launch code is:

```python
from pathlib import Path

image_folder = Path("example_images")
rating_system = MultiRespondentRatingSystem(
    str(image_folder),
    num_respondents=120,
    images_per_person=50,
)
rating_system.show_interface()
```

Run Jupyter from the repository root so that the relative image path resolves correctly.

## Input and output

Input images should use unique filenames. The notebook creates assignment records, progress files, and final response files. Final respondent results are exported as UTF-8 CSV files; assignment and usage summaries are stored in an Excel workbook.

Before data collection, test the full workflow with non-sensitive sample images and a test respondent. Confirm that the number of available images is sufficient for the requested assignment settings.

## Privacy and research-data notice

This repository contains software only. It does not include study images, participant identities, ratings, or research results. Do not commit the generated `评分结果` directory or any files containing personal or confidential research data. Use participant codes instead of real names wherever possible and follow the ethics approval and data-management plan for the study.

## Citation

Citation metadata are provided in `CITATION.cff`. On GitHub, the repository's **Cite this repository** panel can generate a software citation from that file.

For a permanent citable record, connect the public GitHub repository to Zenodo, create a release, and cite the DOI issued by Zenodo. After a DOI is available, add it to both `CITATION.cff` and the manuscript's Data/Code Availability statement.

Suggested citation before a DOI is issued:

> Zhao, J. (2026). *Street-view Affective Rating System* (Version 1.0.0) [Computer software].

## License

This project is released under the MIT License. See `LICENSE`.

## 中文使用说明

本仓库用于公开街景图像情感评分程序，不包含研究图片、受访者信息或评分结果。请将待评分图片放入 `example_images`，从仓库根目录启动 Jupyter，并运行 notebook。正式调查前请使用非敏感样例完成一次全流程测试。生成的 `评分结果` 文件夹不得上传至公开仓库；建议使用受访者编号，不使用真实姓名。

## Author

Jingjing Zhao  
ORCID: [0009-0002-7522-866X](https://orcid.org/0009-0002-7522-866X)
