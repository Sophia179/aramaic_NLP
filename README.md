# NLP for Modern Western Aramaic (Maaloula dialect)
Here will soon be description of Natural Language Processing tools for Maaloula dialect of Modern Western Aramaic.

Modern Western Aramaic is an endangered Semitic language spoken in several villages near Damascus, Syria. It is divided into three dialects depending on the village in which it is or was spoken: Maaloula, Bax'a and Jubb'adin. These NLP tools were created for Maaloula dialect. This work is my graduate work at HSE and its full text is available above in Russian. 

## List of NLP tools 
1. **Morphological parser.** This parser was created via `UniParser`. It returns lemma, part-of-speech tag and grammatical characteristics for each word given.  
  
   How to use:  
   If `UniParser` is not installed, you can install it via `pip`:  
   ```pip3 install uniparser```

   Then initialise `Analyzer()` and load grammar (i. e. `lexemes.txt` and `paradigms.txt` files which should be placed in the same folder):
   ```
   a = Analyzer()  
   a.load_grammar()
   ```
   After that you can pass to parser one word or a list of words which it will analyse:
   ```
   analyses = a.analyze_words('ġamlax')
   for ana in analyses:
      print("wordform: ", ana.wf)
      print("lemma: ", ana.lemma)
      print("grammatical features: ", ana.gramm)
      print("glossed wordform: ", ana.wfGlossed)
      print("glosses: ", ana.gloss)
   ```
   Output:
   ```
   wordform: ġamlax
   lemma: ġamla
   grammatical features: NOUN,POSS.2ms,Sg,m
   glossed wordform: ġaml-ax
   glosses: STEM=2ms
   ```
     
   You can also pass a list of words and specify the output format (`xml`, `json` or `connl`):
   ``` 
   analyses = a.analyze_words(['ana', 'xett', 'batt', 'ṯinaġelča'], format='xml')
   ```
   
   **Evaluation tool for morphological parser** consists of two functions: the first one prepares gold annotation (which is stored in `annotation.txt`) in certain format, the second one returns dataframe with number and percentage of correct lemmata, part-of-speech tags and grammatical features.  
   For a more detailed description see `aramaic_uniparser+evaluation_tool.ipynb`.
      
   For how file `lexemes.txt` was prepared, see `aramaic_uniparser_behind_the_scenes.ipynb`. MASC data can be found on https://zenodo.org/records/5814744#.Yd1M7mhKhPY.

         
3. **Glossing tool.** It is based on `UniParser`. The glossing tool is a function which returns a glossed version for a given text. The output consists of line with morphological segmentation and line with morphological annotation according to glossing rules developed by research group "Grammar of Neo-Aramaic languages" (HSE). Currently the most of stems are glossed as "STEM" but later they will be replaced with English translations. 
  
   How to use:  
   Function takes `.txt` file with text which needs to be annotated. For example of usage see `glossing_tool+evaluation_tool.ipynb`.
   
   **Evaluation tool for glossing tool** is also a function. It takes two obligatory arguments: `.txt` files of glossed text and gold glossed standard. There is also one optional argument which enables to see which words were glossed and segmentated incorrectly. Evaluation tool returns percentage of words with correct morphological segmentation and morphological annotation. For example of usage also see `glossing_tool+evaluation_tool.ipynb`.

    
5. **Modern Western Aramaic parallel annotated multimedia corpus.** Corpus of Maaloula dialect was created via `tsakorpus` platform. Currently it contains only texts in Maaloula dialect. It supports search on wordforms, lemmata, part-of-speech tags, grammatical characteristics (and their combinations). Each sentence is supplied with German translation and audiofile (all audiofiles were taken from MASC dataset). Subcorpora can also be selected based on metadata.  

   Corpus is available per link: https://corpora.iling-ran.ru/aramaic_corpus  
   GitHub repository for corpus: https://github.com/Sophia179/tsakorpus_aramaic  
   For how `.json` files were prepared and for plots with some statistics see `corpus_behind_the_scenes+plots.ipynb`

### Links
[The Maaloula Aramaic Speech Corpus (MASC): From Printed Material to a Lemmatized and Time-Aligned Corpus](https://aclanthology.org/2022.lrec-1.699) (Eid et al., LREC 2022)  
Research group "Grammar of Neo-Aramaic languages": https://iocs.hse.ru/grammararamaic/
