# tsundere-ai-detector
This is a fun project I'm making. From analyzing a manga panel, can an AI fully detect whether a character is a Tsundere or not?

The basic project structure is (sort of) simple. A visual branch, using YOLOv8n will detect facial indicators for a Tsundere character (blushing, anime anger vein, etc.) and also tropes that a Tsundere would enact. An NLP branch, using manga-ocr and DistilBERT will pick up and analyze the language used in the panel by a character, and then classify it under a few Tone Classifier categories. These will then go through a Fusion classifier and then mathematically display a number that will then translate to a yes/no answer on whether the character(s) in the manga panel is/are a tsundere.
