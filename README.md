# SpellChecker_KorVer </br>
Korean Spell Correction program made by YongminYoo who work as Korean NLP researcher. </br></br>
Copyrightⓒ2019 YongminYoo All rights reserved</br>


# Overview </br>
Based on Peter Norvig's Edit Distance idea and idea of RNN series to figure out the context and pick the closest query. </br>
This spell checker module is Korean Language Version made by YongminYoo.</br>
If you have any questions, please contact me here. (yoong952@gmail.com) </br>


# Contents </br>

## ● Pre-processing</br>

### 1 . Clean Text</br>
#### clean.py</br>
1-1. Remove stopwords , punctuations.</br>
1-2. Normalization sentences</br>

## ● Methodology</br>

### 2 . Make dictionary</br>
#### MakeDict.py
2-1-1. Split by morphs(Use Kkma morphs module which modules are in Konlpy) </br>
2-1-2. Split by whitespace</br>
2-2. Make Dictionary which are split by previous work</br>

### 3 . Make TestSet</br>
#### MakeTest.py
3-1. Generates a typo for each tenth syllable.

### 4 . Find incorrect word</br>
4-1. If words isn't exist in dictionary , consider that word is incorrect word.</br>
4-2. Find candidate word using Peter Novig's idea , Edit distance(ED). In this research we consider ED less than 1.7 </br>
(I will try to find which ED score is effective with optimizing algorithm , It will be included in the next research topic.) </br>
4-3. The context is identified using the RNN sequence algorithm, and the most appropriate word among the candidate words is selected as the correct word.</br>


## ● Evaluation</br>
#### Evaluation.py</br>
5-1. Make training set (90%) , test set(10%) randomly. </br>
5-2. Calculate precision , recall value. </br>
5-3. Finally, calculate F1 score. </br>


# Result </br>
Our method showed an F1 score of 93.6%. </br>
Future studies </br>
1) How to deal with actual words that are not in the dictionary?</br> 
2) How to overcome RNN series long term dependency error?</br>
3) When using Edit distance, what is the most optimized ED number?</br>
4) How to solve speed problem?</br>


## Contribution </br>
- Peter Novig의 Edit Distance를 한글에 적용 한 첫번째 논문 </br>
- 이전 연구와 달리 한글을 자모 단위로 split 해서 "안녕" 을 2음절로 인식하지 않고 "ㅇㅏㄴㄴㅕㅇ"으로 인식하게 함</br>
- Context를 고려하지 않는 Rule base 기반인 Edit Distance의 문제점을 DeepLearning을 이용해 최적의 값을 찾았다.</br>
      - "현대는 ㅈ동차 참 잘만들어"</br>
      - "올해 사법시험이 ㅈ동차 합격했어!"</br>
- 라는 두 문장을 고쳐야 할 경우, ED의 경우 둘 다 자동차로 고치게 되나 RNN계열의 알고리즘은 windowsize에 따라 앞 뒤 문장을 파악해 최적의 답을 찾을 수 있게 됨.</br>
- Edit distance 와 RNN의 조합으로 스펠링체커를 만든 첫번째 논문.
- Edit distance의 숫자가 커지지않거나 RNN의 windowsize가 커지지 않는다면 속도문제도 해결 됨.
