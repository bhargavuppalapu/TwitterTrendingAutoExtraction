#Prerequisite software

This application is built using Microsoft .Net Framework4 so it needs the .Net Framework 4 or above. 
Usually Windows 8 or above will have the .Net v4.0.
You must be able to download and install the .Net Framework 4 from http://www.microsoft.com/en-in/download/details.aspx?id=17851

#3rd Party tools used

1. Stanford PTB Tokenizer  
	http://nlp.stanford.edu/nlp/javadoc/javanlp/edu/stanford/nlp/process/PTBTokenizer.html
2. POS tageer by open NLP. 
	http://opennlp.apache.org/documentation/manual/opennlp.html#tools.tokenizer
3. Stanford Named Entity Recognizer 
	http://nlp.stanford.edu/ner/
4. IKVM for portingt he Java jar files to .Net dlls. 
	http://www.ikvm.net/

	
#Usage

1. Give the information of the input file which has the tweets in the cofig file.
2. Give the information of the output folder where you want to save the results.

The Hashtag extraction and segmentation results are stored in the file "output_HashTagSplit.txt" in the output folder. The Trends extracted are stored in the file "output_Trends.txt" in the output folder.

You can go to the DemoTest.c file and run the code from there. 

Need to specify the config file path. Config file "config.ini" has the Following details.

1. Hash Tag Splitter ModelFile -- Model file for the Viterbi algorithm which contains the word probability list.
2. InputFile -- File with the input text.
3. OutPutFolder -- Folder in which we want to output the results. The results are written into a text file.
4. NamesForTrends -- Give the names for which you want to know the trends. One name per line.
5. POSTaggerModelFile -- POS tagger Model file path.
6. NamedEntityRecognizerModelFile -- NER Model file path.

Below are the details of the classes we want to use for the specific task. Using config file because if we want to use another algorithm for 
specific task we can handle the same using the cofiguration.

1. HashTagSplitter -- Class Name of the Hash tag splitter.
2. Tokenizer -- Tokenizer class name.
3. POSTagging -- POS tagging class file name.
4. NamedEntityRecognizer -- NamedEntityRecognizer Class File.
5. TrendExtractor -- TrendExtractor Class File name

#Future work

1. Use the parser for finding the trends so that we only can extract the trends that are having relation with the person. Currenytly using POS tags JJ/VBJ/NN that are present around the name for the relevance of the trend.
2. Word Sense Disambiguation so that similar trends can be clustered together.

