## 데이터 전처리 (Data Preparation)

`re` : regular expression (정규 표현식)

```python
import re
```

https://medium.com/@originerd/%EC%A0%95%EA%B7%9C%ED%91%9C%ED%98%84%EC%8B%9D-%EC%A2%80-%EB%8D%94-%EA%B9%8A%EC%9D%B4-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0-5bd16027e1e0



## Machine Learning

http://research.sualab.com/machine-learning/2017/09/04/what-is-machine-learning.html



## 단어 분석

1. csv --> pd.read_csv()

2. pd.read_csv() --> df    

3. df --> get the text by calling the index   --> returns `string`

   ```python
   df['title'][index]
   ```

   '리벤지포르노(복수 불법촬영물) 단어를 처음 접했을때, 저는 인터넷강국인 한국에서 왜 여성의 공개적 강간과 다름없는 행위가 대대적으로 수사처벌이 안되어왔는지 의심할 수 밖에 없었습니다.\\n리벤지포르노(복수 불법촬영물)의 역사는...'

4. `string` --> `string` # clean up the word

   ```python 
   def preprocessing(text):
       # 개행문자 제거
       text = re.sub('\\n', ' ', text)
       # 특수문자 제거
       # 특수문자나 이모티콘 등은 때로는 의미를 갖기도 하지만 여기에서는 제거했습니다.
       # text = re.sub('[?.,;:|)*~`’!^-_+<>@#$%&-=#}※]', '', text)
       # 한글, 영문, 숫자만 남기고 모두 제거하도록 합니다.
       # text = re.sub('가-힣ㄱ-ㅎㅏ-ㅣa-zA-Z0-9', ' ', text)
       # 한글, 영문만 남기고 모두 제거하도록 합니다.
       # replace와 re.sub의 차이???
       text = re.sub('가-힣ㄱ-ㅎㅏ-ㅣa-zA-Z', ' ', text)
       return text
   ```

   4.1. Check dataframe with cleaned text

   ```python
   sentences = feminist['content'].apply(preprocsseing)
   sentences
   ```

5. Tokenization using Soynlp --> returns a `list` of tokenized words

   ```python
   tokened_content = tokenizer.tokenize(sample_content)
   ```

   ['리벤지포르노', '복수', '불법촬영물', '단어를', '처음', '접했을때', '저는', '인터넷강국인', '한국에서', '왜']

   5.1. take 

6. Remove Stopwords 

   ```python
   def remove_stopwords(text):
     stops = ['를','을','은','는','있습니다','입니다', '그', '년도', '에', '합니다', '가', '했습니다']
     meaningful_words = [word for word in text if not word in stops]
     return ''.join(meaningful_words)
   ```

   '리벤지포르노 복수 불법촬영물  단어 처음 접했때  저 인터넷강국인 한국서 왜 여성의 공개적 강간과 다름없 행위 대대적으로 수사처벌이 안되어왔지 의심할 수 밖 없었습니다'



Pandas - Series (DataType)
