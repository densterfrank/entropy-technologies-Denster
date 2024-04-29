# entropy-technologies-Denster
# Name
### Denster Joseph Frank - Data Scientist
# Project Overview
The project involves the development of a pipeline that leverages either a rule-based or Natural Language Processing (NLP) approach. The primary objective is to process text data, which is obtained via Optical Character Recognition (OCR) from laboratory test results or medical records. The challenge lies in the potential inaccuracies in the OCR output, which is unstructured. The aim is to convert this unstructured data into a structured format, specifically a Python list of dictionaries. Each dictionary will contain three keys: ‘parameter’, ‘value’, and ‘unit’. An example of the desired format is: [{“parameter”: “iron”, “value”: 5.3, “unit”: “mmol/mL”}, …].
# Approach
<img width="691" alt="image" src="https://github.com/densterfrank/entropy-technologies-Denster/assets/87901837/345c9311-1a42-47c4-9b83-ce32ab7ff98a">


## Read Line
#### Function `to_read_txt` is used to read data from txt file

## Read Parameter
#### Function `to_read_json` is used to read data from json file and store in list named `parameter_list`

## Cleaned List
#### Function `makelist_from_lines` is used to store each line as element in the list named `cleaned_list`

## First Filter
This function  `first_filter` contains a data cleaning pipeline that utilizes regex and NLP techniques to remove unwanted lines from a given list of text data. The process involves several steps:

1. **Tokenization**: Each line of text is converted into tokens.
2. **Lowercasing**: All tokens are converted into lowercase for consistency.
3. **Removal of Unwanted Tokens**: Each list of tokens is passed to a function called `remove_unwanted_tokens`, which removes unwanted data such as `(3.5-6.0)` from the list of tokens.
4. **Filtering Criteria**: The filtered lines are determined based on three main conditions:

   - **Condition 1**: `is_word_similar_to_parameters`: Checks whether the line has parameters similar to those specified in a JSON file.
   - **Condition 2**: `has_numbers`: Determines if the line contains any numbers or floats.
   - **Condition 3**: `detect_unit`: Checks if there are any units present in the line, which are identified by characters like `/` and `%`.

The unwanted lines are removed based on these conditions, and the filtered lines are stored in a list called `filtered_data`.

## Second Filter
This function, `second_filter`, serves as the second layer of filtering in the cleaning process. Each line of data is passed into two separate functions, `verify`, which filter out unwanted data based on specific conditions.

## Conditions for Filtering

### Condition 1: Contains Special Symbols

The function `contains_special` filters data if it contains special symbols such as `<`, `>`, `|`, or `-`. 

### Condition 2: Contains "AND" or "BETWEEN"

The function `contains_and_or_between` filters data if it contains the words "and" and "between" within the line.

After passing through these conditions, the filtered data is stored in a list called `new_filtered_data`.

## Information Extaction
This function is designed to extract three types of information from a cleaned line of text.

### 1. Parameter Name
- The function `find_similar_words` is utilized to detect words similar to a given word from a JSON file.
- This function implements cosine similarity logic to determine similar words and returns a list of words with their respective similarity scores.
- The function `highest_similarity` is then employed to identify the word with the highest similarity score among all.

### 2. Unit
- The function `detect_unit` is responsible for identifying any units present in the line.
- Units are recognized by characters such as `/` and `%`.

### 3. Value
- Observation suggests that the value is consistently located beside the unit.
- Logic has been implemented to check both the left and right sides of the list to detect the value.
- The `isinstance` function is used for this purpose.

- The extracted parameter, value, and unit are stored in a list of dictionaries named `main_dic`.

## Remove Duplicates
<img width="415" alt="image" src="https://github.com/densterfrank/entropy-technologies-Denster/assets/87901837/6e5c501b-bfd0-413c-8db5-2d520f306cd7">


As we can see from the image that the parameter is not unique, So to remove duplicate we have used function called `remove_duplicate_parameter`
## Final Output

