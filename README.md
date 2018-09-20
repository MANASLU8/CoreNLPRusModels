# CoreNLPRusModels
Stanford Tagger and NN Dependency Parser Models for Russian Language

1. Link to parser models https://drive.google.com/drive/folders/0B4TmAgcGLMriS3hhTkV5VEFPVEU?usp=sharing  
2. Link to tagger models and lemmatization resources https://drive.google.com/drive/folders/0B4TmAgcGLMriMG96cFZSSWhWcEU?usp=sharing

# Getting Started with Pipeline for Russian language

1. Clone  CoreNLP from the project repository: https://github.com/MANASLU8/CoreNLP.   

2. Download resources for lemmatization 'dict.tsv', tagger and parser models using links in section 'CoreNLPRusModels' above.  

3. Build the project and run the Launcher  (edu.stanford.nlp.international.russian.process.Launcher).  
Obligatory Launcher parameters are the following:  
-tagger, filepath to POS-tagging model russian-ud-pos.tagger;  
-taggerMF, filepath to POS-tagging model  russian-ud-mf.tagger, which outputs POS-tags  with inflectional morphological features (according to UD v.2 http://universaldependencies.org/u/feat/index.html);  
-mf, if this flag is True, inflectional morphology is writter to the FEATS field of the CoNLL annotations;  
-parser, dependenct parser model, inventory of syntactic relations meets UD v.2 (http://universaldependencies.org/u/dep/index.html), better start with the model nndep.rus.modelMFWiki100HS400_80.txt.gz, which uses embeddings, trained on Wikipedia dump;  
-pLemmaDict, filepath to dict.tsv, preferrably to put it to /CoreNLP/src/edu/stanford/nlp/international/russian/process directory;  
-pText, filepath to input file, encoding = UTF-8; /home/filepath/input_file.txt  
-pResults, filepath to output file '.conll', format = CoNLL-U (http://universaldependencies.org/format.html).  

4. Running from console example:  
java -Xmx8g edu.stanford.nlp.international.russian.process.Launcher -tagger /home/comp/eclipse-workspace/CoreNLP/russian-ud-pos.tagger -taggerMF /home/comp/eclipse-workspace/CoreNLP/russian-ud-mf.tagger -pLemmaDict /home/comp/eclipse-workspace/CoreNLP/src/edu/stanford/nlp/international/russian/process/dict.tsv -parser /home/comp/eclipse-workspace/CoreNLP/nndep.rus.modelMFWiki100HS400_80.txt.gz -pText /home/comp/eclipse-workspace/CoreNLP/input.txt -pResults /home/comp/eclipse-workspace/CoreNLP/output.conll -mf  

5. Other Requirements  
Java 1.8  
allocate at less  5 Gb for JVM:  -Xmx5g  
input file encoding: UTF-8  
