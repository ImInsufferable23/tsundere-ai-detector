# tsundere-ai-detector
This is a fun project I'm making. From analyzing a manga panel, can an AI fully detect whether a character is a Tsundere or not?

The basic project structure is (sort of) simple. A visual branch, using YOLOv8n will detect facial indicators for a Tsundere character (blushing, anime anger vein, etc.) and also tropes that a Tsundere would enact. An NLP branch, using manga-ocr and DistilBERT will pick up and analyze the language used in the panel by a character, and then classify it under a few Tone Classifier categories. These will then go through a Fusion classifier and then mathematically display a number that will then translate to a yes/no answer on whether the character(s) in the manga panel is/are a tsundere.

The repo, by the end, should hopefully look like this (I asked Claude to generate a notepad diagram for how it will roughly look like once I'm done):


tsundere-detector/
├── data/
│   ├── panels/              
│   ├── annotations/          
│   └── splits/               
│
├── src/
│   ├── data/
│   │   ├── manga109_loader.py
│   │   ├── panel_extractor.py
│   │   └── dataset.py
│   │
│   ├── models/
│   │   ├── character_model.py
│   │   ├── expression_model.py
│   │   ├── ocr_model.py
│   │   ├── nlp_model.py
│   │   └── fusion_model.py
│   │
│   ├── training/
│   │   ├── train_visual.py
│   │   ├── train_nlp.py
│   │   └── train_fusion.py
│   │
│   ├── inference/
│   │   ├── pipeline.py
│   │   └── visualize.py
│   │
│   └── utils/
│       └── image_utils.py
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_visual_branch.ipynb
│   ├── 03_nlp_branch.ipynb
│   └── 04_demo.ipynb
│
├── scripts/
│   ├── prepare_annotations.py
│   └── run_inference.py
│
├── configs/
│   ├── pipeline.yaml
│   └── label_studio_config.xml
│
├── tests/
│   └── test_pipeline.py
│
├── docs/
│   └── annotation_guide.md
│
├── annotation_schema.json
├── requirements.txt
├── requirements_colab.txt
└── README.md
