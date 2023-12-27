## About:
Contributed to "CaML: Carbon Footprinting of Household Products with Zero-Shot Semantic Text Similarity," improving accuracy by 3% and reducing time complexity by 60 times with FAISS-IVF for search and retrieval, and a fine-tuned all-mpnet-base-v2 model achieving 64.55% accuracy

## Dataset:
The CaML study utilized data from three primary sources to achieve its objectives. Firstly, it included an extensive compilation of NAICS descriptions, encompassing over 20,000 rows across 1,016 codes, which exhibited a varied distribution of definitions per code. Secondly, the study incorporated USEEIO CO2 emissions data for each of these NAICS codes, providing a crucial measure of environmental impact. Lastly, it involved product industry annotations for about 6,000 grocery items, which were categorized under 210 different NAICS codes.


## Data preprocessing:
The process begins with lower casing, which ensures uniformity in text by converting all letters to lowercase. This is followed by the removal of punctuation and numbers.
Removing Stop words:
	
Lemmatization
	
Key Phrase Extraction
	
YAKE

KeyBERT

Amazon Comprehend

Additionally, there is a mapping of CO2e/$ for each NAICS code’s description, providing an environmental impact assessment. Finally, the merged file is filtered to contain only descriptions of NAICS codes in the product annotations.

# Expriments and their Result Table:

<img width="644" alt="image" src="https://github.com/SANGAMITHRAMURUGESAN/Carbon-Footprint-Estimation-Leveraging-Data-Mining-Techniques/assets/78456699/82e2c242-53eb-4aac-b4de-095bed08de86">
