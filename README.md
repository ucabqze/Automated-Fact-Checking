# Automated-Fact-Checking
this project is to develop information retrieval and data mining methods to assess the veracity of a claim. Specifically, the automated fact checking project consists of three steps: relevant document retrieval, evidence sentence selection, and claim veracity prediction.



Important Information
================
In this section, point out any important information that is valuable for the evaluator to know before evaluating this submission

Provided supplementary files
===================
In this section, define the filename of different files that are included in this submission followed by a description of the information in the file.


The answer for Q2 and Q3:
Q2/files/Q2_vector_space.csv
Q3/files/Q3_dirichlet.csv
Q3/files/Q3_jelinek_mercer.csv
Q3/files/Q3_laplace.csv
Q3/files/Q3_unigram.csv

Others:
Q1/files/term_count.csv : A CSV file that records the words count.
Q4/files/q4_docs.csv: it records the first 1000 file retrieved for negative sampling on train data in Q4
Q4/files/q4_relavent_docs_dev.csv: it records the first 10 file retrieved for negative sampling on development data in Q4
Q4/files/1000_sample_k1_train: it records the samples to train the logistic regression model.




Missing supplementary files
===========================
!!!important: 

'fever data files' 
There is a file named 'wiki_id_text', which records all the id and text for wiki pages. This file is widely used in my code. Please use the parse_wiki from      https://github.com/QiangAIResearcher/Fact-Extraction-and-Verification/blob/master/fever_io.py   to generate this file. and please download all the FEVER 1.0 Dataset from http://fever.ai/resources.html. Or you can run 'Q1/code/convert_data.ipynb'. All of these files mentioned above will be called as fever data files later.

'glove model':
please download Wikipedia 2014 + Gigaword 5 (6B tokens, 400K vocab, uncased, 50d, 100d, 200d, & 300d vectors, 822 MB download): glove.6B.zip and Common Crawl (42B tokens, 1.9M vocab, uncased, 300d vectors, 1.75 GB download): glove.42B.300d.zip from    https://nlp.stanford.edu/projects/glove/   they will be called glove model later.

'inverted index data':
Q2/files/inverted_word_dictionary.txt: it records the inverted index dictionary
Q2/files/doc_length_list.txt: it records the documents length of each documents in wikipedia 
This two are too large. Please run 'Q2/code/q2toq4_invertedIndex.ipynb' to generate them 

'Q6':
Q6/files/q6_glove_model: it record the re-constructed Glove model for Q6
Q6/files/q6_vocab: it records a temp vocabulary for word embedding for Q6
Q6/files/q6_embedding_matrix: it records a embedding matrix for Q6
Q6/files/q6_input_x_train: the train data features
Q6/files/q6_input_x_dev: the development data features
Q6/files/q6_input_y_train: the train data labels
Q6/files/q6_input_y_dev: the development data labels
They are too large. Please run q6.ipynb from first to last cells.

Code files
==========
'Q1/code/q1.ipynb': this is the code for subtask 1
'Q1/code/convert_data.ipynb': this is convent wikepages jsonl file to txt
'Q2/code/q2.ipynb': this is the code for subtask 1
'Q2/code/q2toq4_invertedIndex.ipynb': this code produces inverted index dictionary for q2-q4
'Q3/code/q3.ipynb': this is the code for subtask 1
'Q4/code/q4&5.ipynb': this is the code for subtask 4 and subtask 5
'Q5/code/q4&5.ipynb': this is the code for subtask 4 and subtask 5
'Q6/code/q6.ipynb': this is the code for subtask 1



Running the code
================

!!!To run the code, please put the relevant files to the right route and then run the code. With fever data files and glove model, the code can be ran if you open the notebooks from q1.ipynb, q2toq4_invertedIndex.ipynb, q2.ipynb to q6.ipynb and run the notebook from first to the last cel, but to save the running time, please follow the following instructions.

Q1: You can run q1.ipynb from the first cell with 'fever data files'. If you want to start from 'Step2: Zips Law visualisation', please put the 'Q1/files/term_count.csv' to your direction.

Q2: To run 'q2.ipynb', you need to put'fever data files', 'Q2/files/inverted_word_dictionary.txt' and 'Q2/files/doc_length_list.txt' to your direction. If you want to reproduce this file please run 'Q2/code/q2toq4_invertedIndex.ipynb'.

Q3: To run 'q3.ipynb', you need to put 'Q2/files/inverted_word_dictionary.txt' and 'Q2/files/doc_length_list.txt' to your direction. If you want to reproduce this file please run 'Q2/code/q2toq4_invertedIndex.ipynb'. 

Q4&Q5:

To run ' 1. Prepare relevant docs ', you need 'Q2/files/inverted_word_dictionary.txt' and 'Q2/files/doc_length_list.txt' as mentioned in Q2 and Q3. If you skip this step, you need to load Q4/files/q4_docs.csv for later steps.

To run ' 2. *Import Data and Models', you need all the fever data files and 'q4_docs.csv'

To run '3. Negative Sampling', run step 2 firstly. If you skip this step, please put the Q4/files/1000_sample_k1_train to right direction.

To run '4.* Sentence Embedding', run step 2 firstly. you also need 'Glove model' and 'Q4/files/1000_sample_k1_train'

To run '5. *Logistic Regression', run step 2,4.

To run '6. *Evaluation', run step 2,4,5. You also need 'q4_relavent_docs_dev.csv'

To run '7. *Learning Rate Analysis', run step 2,4,5,6

To run Q5, run Q4 firstly.

Q6: In q6.ipynb, step 2 is preparing the data and step 3 is train the model.
You can only run from the first cell, you need fever data files and Glove model.
