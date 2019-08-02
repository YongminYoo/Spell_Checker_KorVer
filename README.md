# Spell_Checker_KorVer </br>
Korean Spell Correction program made by YongminYoo who work as Korean NLP researcher. </br>


# Overview </br>
Based on Peter Norvig's Edit Distance idea and idea of RNN series to figure out the context and pick the closest answer. </br>
This spell checker module is Korean Language Version.</br>

# Contents </br>

## ● Pre-processing</br>

### - Clean Text</br>
#### clean.py</br>
1-1. Remove stopwords , punctuations.</br>
1-2. Normalization sentences</br>

## ● Methodology</br>

### 2.Make dictionary</br>
#### MakeDict.py
2-1-1. Split by morphs(Use Kkma morphs module which modules are in Konlpy) </br>
2-1-2. Split by whitespace</br>
2-2. Make Dictionary which are split by previous work</br>

### 3.Make TestSet</br>
#### MakeTest.py
3-1. Generates a typo for each tenth syllable.

### 4.Find incorrect word</br>
4-1. If words isn't exist in dictionary , consider that word is incorrect word.</br>
4-2. Find candidate word using Peter Novig's idea , Edit distance(ED). In this research we consider ED less than 1.7 (ED < 1.7)</br>
4-3. The context is identified using the RNN sequence algorithm, and the most appropriate word among the candidate words is selected as the correct word.</br>


## ● Evaluation</br>
5-1. Make training set (90%) , test set(10%) randomly. </br>
5-2. Calculate precision , recall value.
5-3. Finally, calculate F1 score.


