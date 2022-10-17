# BERT-constructs-NER
 BERT training and evaluation on our custom annotated data for constructs.\n
Run the files in sequential numbering of 1,2,3 and then 4.Best environment to run is google collab,  as because of version issues, there might be some errors and debugging needed to be done if execeuting on Jupyter Notebook ./n
Step 1 preprocesses the data to extract only the abstracts and titles of the papers in a csv file, from the full excel file containing additional metadata like ISSN,DOI,Author ID etc./n
Step 2 takes the csv file generated from the 1st step , and the model is pretrained on the vocabulary of the abstract sentences of more than 50,000 paper abstracts to give tokenization and training weights for the actual fine-tuning. This process consumes the most amount of resources./n
After language modeling in step 2, we move on to the actual fine-tuning in step 3, where we input our training data for NER to the model. The model is trained based on the weihts and tokens generated from the previous step to generate predictions in a pickle(.pkl) file./n
After generating predictions, we automate the process in the last step by predicting on each abstract of the big excel file, and then adding the respective predictions in a separate column in the excel file,  respectively for all abstracts./n
