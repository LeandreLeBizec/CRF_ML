# Text Tagging Project

## About

This project aims to process a dataset of sentences and tag specific entities such as city names and days of the week. The workflow includes loading data from a file, tagging words in the sentences, and writing the processed data into new files. The project uses a combination of Python, NumPy, Pandas, and Scikit-learn to handle data processing and manipulation.

## Project Structure

- `atis.train`: Input file containing sentences and their respective tags (input words and corresponding POS tags).
- `uscities.csv`: CSV file containing a list of US cities for tagging purposes.
- `atis.tain`, `atis.test`: Output files with annotated sentences, POS tags, and additional tags (city or day).

## Main Components

### Data Loading

The function `load(file)` reads the `atis.train` file line by line, splitting words and their POS tags, and storing them into two lists:
- `Sentences (X)` : List of words.
- `PostTags (Y)` : Corresponding POS tags for each word.

### Data Splitting

The dataset is split into training and testing sets using `train_test_split`, with 50% of the data for each.

### City Name Tagging

The function `USCities()` loads a list of US cities from the `uscities.csv` file, processes the names (converting to lowercase and replacing spaces with hyphens), and returns the list.

### Sentence Tagging

The function `cityTag(Sentences)` takes the list of sentences and tags each word as either:
- `city` if the word is a recognized US city,
- `day` if the word is a day of the week,
- `O` if the word doesn't match any of these categories.

### Output Writing

The `write(filename, Sentences, PostTags, Tags)` function writes the processed sentences, original POS tags, and new tags (city or day) into output files (`atis.tain` and `atis.test`).

## How to Run

1. Place the required data files (`atis.train` and `uscities.csv`) in the `Data` directory.
2. Run the script to process the data and generate the tagged output files.
3. You can test your model with [evaluation.pl](https://github.com/LeandreLeBizec/CRF_ML/blob/main/Data/evaluation.pl).
