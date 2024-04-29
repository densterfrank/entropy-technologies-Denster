# entropy-technologies-Denster
# Name
### Denster Joseph Frank - Data Scientist
# Project Overview
### The project involves the development of a pipeline that leverages either a rule-based or Natural Language Processing (NLP) approach. The primary objective is to process text data, which is obtained via Optical Character Recognition (OCR) from laboratory test results or medical records. The challenge lies in the potential inaccuracies in the OCR output, which is unstructured. The aim is to convert this unstructured data into a structured format, specifically a Python list of dictionaries. Each dictionary will contain three keys: ‘parameter’, ‘value’, and ‘unit’. An example of the desired format is: [{“parameter”: “iron”, “value”: 5.3, “unit”: “mmol/mL”}, …].
# Approach
<img width="473" alt="image" src="https://github.com/densterfrank/entropy-technologies-Denster/assets/87901837/06d14f53-d895-41fe-af38-d997df0bc09d">

## Read Line
#### Function *to_read_txt* is used to read data from txt file

## Read Parameter
#### Function *to_read_json* is used to read data from json file and store in list named *parameter_list*

## Cleaned List
#### Function *makelist_from_lines* is used to store each line as element in the list named *cleaned_list*

## First Filter

## Second Filter

## Remove unwanted tokens

## Information Extaction

## Remove Duplicates

## Final Output

