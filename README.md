# entropy-technologies-Denster
# Name
### Denster Joseph Frank - Data Scientist
# Project Overview
### The project involves the development of a pipeline that leverages either a rule-based or Natural Language Processing (NLP) approach. The primary objective is to process text data, which is obtained via Optical Character Recognition (OCR) from laboratory test results or medical records. The challenge lies in the potential inaccuracies in the OCR output, which is unstructured. The aim is to convert this unstructured data into a structured format, specifically a Python list of dictionaries. Each dictionary will contain three keys: ‘parameter’, ‘value’, and ‘unit’. An example of the desired format is: [{“parameter”: “iron”, “value”: 5.3, “unit”: “mmol/mL”}, …].
# Approach
<img width="473" alt="image" src="https://github.com/densterfrank/entropy-technologies-Denster/assets/87901837/06d14f53-d895-41fe-af38-d997df0bc09d">

## Read Line
#### Function `to_read_txt` is used to read data from txt file

## Read Parameter
#### Function `to_read_json` is used to read data from json file and store in list named `parameter_list`

## Cleaned List
#### Function `makelist_from_lines` is used to store each line as element in the list named `cleaned_list`

## First Filter
This function  contains a data cleaning pipeline that utilizes regex and NLP techniques to remove unwanted lines from a given list of text data. The process involves several steps:

1. **Tokenization**: Each line of text is converted into tokens.
2. **Lowercasing**: All tokens are converted into lowercase for consistency.
3. **Removal of Unwanted Tokens**: Each list of tokens is passed to a function called `remove_unwanted_tokens`, which removes unwanted data such as `(3.5-6.0)` from the list of tokens.
4. **Filtering Criteria**: The filtered lines are determined based on three main conditions:

   - **Condition 1**: `is_word_similar_to_parameters`: Checks whether the line has parameters similar to those specified in a JSON file.
   - **Condition 2**: `has_numbers`: Determines if the line contains any numbers or floats.
   - **Condition 3**: `detect_unit`: Checks if there are any units present in the line, which are identified by characters like `/` and `%`.

The unwanted lines are removed based on these conditions, and the filtered lines are stored in a list called `filtered_data`.

## Second Filter

## Remove unwanted tokens

## Information Extaction

## Remove Duplicates

## Final Output

