# NLP for Modern Western Aramaic (Maaloula dialect)
Here will soon be description of Natural Language Processing tools for Maaloula dialect of Modern Western Aramaic.

Modern Western Aramaic is an endangered Semitic language spoken in several villages near Damascus, Syria. It is divided into three dialects depending on the village in which it is or was spoken: Maaloula, Bax'a and Jubb'adin. These NLP tools were created for Maaloula dialect. This work is my graduate work at HSE and its full text is available above in Russian. 

## List of NLP tools 
1. **Morphological parser.** This parser was created via `UniParser`. It returns lemma, part-of-speech tag and grammatical characteristics for each word given.  
  
   How to use:
   If `UniParser` is not installed, you can install it via `pip`:
   ```pip3 install uniparser```

   Then initialise `Analyzer()` and load grammar (i. e. `lexemes.txt` and `paradigms.txt` files which should be placed in the same folder):
   ```a = Analyzer()
   a.load_grammar()
   ```
   After that you can pass to parser one word or a list of words which it will analyse:
   ```analyses = a.analyze_words('xalpa')
   analyses = a.analyze_words(['ana', 'xett', 'batt', 'ṯinaġelča'])```
   
   **Evaluation tool for morphological parser** (here will be description soon)
     
3. **Glossing tool.** It is based on `UniParser`. The glossing tool return a glossed version for given text which consists of line with morphological segmentation and line with morphological annotation. This tool is based on glossing rules developed by research group "Grammar of Neo-Aramaic languages" (HSE).  
  
   *How to use:* (here will be description soon)
   
   **Evaluation tool for glossing tool** (here will be description soon)

5. **Modern Western Aramaic parallel annotated multimedia corpus.** Corpus of Maaloula dialect was created via `tsakorpus` platform. Currently it contains only texts in Maaloula dialect. It supports search on wordforms, lemmata, part-of-speech tags, grammatical characteristics (and their combinations). Each sentence is supplied with German translation and audiofile (all audiofiles were taken from MASC dataset). Subcorpora can also be selected based on metadata.  
   Corpus is available per link: (here will be a link soon)

### Links
Here will soon be links!
