## About:
Contributed to "CaML: Carbon Footprinting of Household Products with Zero-Shot Semantic Text Similarity," improving accuracy by 3% and reducing time complexity by 60 times with FAISS-IVF for search and retrieval, and a fine-tuned all-mpnet-base-v2 model achieving 64.55% accuracy

## Dataset:
The CaML study utilized data from three primary sources to achieve its objectives. Firstly, it included an extensive compilation of NAICS descriptions, encompassing over 20,000 rows across 1,016 codes, which exhibited a varied distribution of definitions per code. Secondly, the study incorporated USEEIO CO2 emissions data for each of these NAICS codes, providing a crucial measure of environmental impact. Lastly, it involved product industry annotations for about 6,000 grocery items, which were categorized under 210 different NAICS codes.


## Data preprocessing:
The process begins with lower casing, which ensures uniformity in text by converting all letters to lowercase. This is followed by the removal of punctuation and numbers.
Removing Stop words:
	Since the  product descriptions are in English, we systematically remove words that are frequently used but have little semantic significance for the purposes of our analysis. These consist of terms like "a," "the," and "and."
Lemmatization:
	This process transformed words to their root forms, leading to greater consistency across the dataset and enabling more efficient analysis in subsequent stages. Here the data in the column (descriptions) were lemetized.
Key Phrase Extraction:
	The process of automatically identifying significant terms that best capture the topic or primary ideas of a document or text is known as "key phrase extraction". Here we experimented with three methods:
	YAKE: It is an unsupervised, lightweight method.It focuses on automatic keyword extraction from single documents utilizing statistical text features for keyword extraction.When experimented with YAKE. Too many keywords were extracted which actually created noise in the document. Hence this method was dropped.
	KeyBERT: KeyBERT generates document embeddings using sentence-transformers. It compares pretrained multilingual models to unsupervised models for keyword extraction. When tried with keyBERT very few keywords were extracted which was not sufficient enough. Hence this method was also dropped. 
	Amazon Comprehend: After reaching out to the author of the paper and based on his suggestion Amazon Comprehend was tried. It is used for semantic analysis of patents.
It features capabilities such as clustering patents for topic modeling and identifying key terms/phrases.This method gave us better results.
Removing duplicates, least common and most common words: Duplicate words are removed to avoid redundancy. The process also involves eliminating the most common generic words and the least common non-dictionary words to refine the dataset's relevance for example “manufacture”, “ product”. Products with less than five words and those with fewer than two consensus votes are dropped to maintain data quality. 
Additionally, there is a mapping of CO2e/$ for each NAICS code’s description, providing an environmental impact assessment. Finally, the merged file is filtered to contain only descriptions of NAICS codes in the product annotations.

# Expriments and their Result Table:

<img width="644" alt="image" src="https://github.com/SANGAMITHRAMURUGESAN/Carbon-Footprint-Estimation-Leveraging-Data-Mining-Techniques/assets/78456699/82e2c242-53eb-4aac-b4de-095bed08de86">
