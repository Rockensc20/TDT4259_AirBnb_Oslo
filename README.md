# TDT4259 - AirBnb Listings Oslo

This repository contains the code for the applied data science group project surrounding the AirBnb listings data from Oslo which can be found [here](https://insideairbnb.com/get-the-data/).

This repository will include seperate Python notebooks for processing the raw dataset, performing analysis on it along with visualizations and one for the feature extraction as well as potentially model training. 

Please use branching when making changes.

## Notebook data_preperation Description

This notebook is used to handle the raw listings dataset and convert/transform it for our use case. Therefore, it inlcudes dropping unnecessary columns, transforming datatypes, filling Nan values as well as one-hot encoding. Encoding was performed to get transform textual data. In addition the amenities list was extracted into a seperate dataframe, the records can be referenced by their listings id. The only Nan rows that were dropped are the ones that were missing a price. For other columns that contained Nan values such as beds or bedrooms assumptions were made based on other columns in the dataset. To review the transformations take a look at the code. They can be excluded from the function *process_listings* which is the most important function in the notebook. New transformations have to be added here. 

**Important note**: A range of listing was missing review / rating data. However, instead of outright dropping these rows, they were encoded as invalid and an additional column was added called *missing_rating_review_data*. If that column contains a 1, then the record should not be used in statistical analysis or sorting of the review data inlcuding the review dates or rating values. 
## CSV Files

After running all cells in the data_preperation notebook the following csv files will be created in the csv subdirectory.

- `listings_processed.csv`: The clean listings dataset ready created with the *process_listings* function
- `amenities_raw.csv`: The amenity data extracted from the column *amenities* in the orginal listings data. One-hot encoded, but not categorized, contains all unique values.
- `amenities_encoded_rankings.csv`: List of the most common amenities found in the amenities data
- `amenities_encoded_categorized.csv`: Ameneties data based on a set of hand-defined / extracted categories, a lot less features then the raw data as it groups the columns.
- Add more files as needed.

## Notes

Any extra notes can be added here

