## 숙제 체크 (파이썬 프로그래밍)

**Code 3 Python functions that generates a random list & shuffle it

```python
def shuffle(list):
    pass

print(shuffle([1,2,3,4,5]))
```

무엇이 잘못 되었는가?

1. docstring 빠짐 
2. list - build-in function
3. Function does return anything

```python
def shuffle0(data):
    temp = data [2]
    data [2] = data [3]
    data [3] = temp
    return data

print (shuffle0(data))
```

무엇이 잘못 되었는가?

원래의 요구사항 : 원래의 리스트가 바뀌지 않고 유지되어야 함

```python 
def shuffle0(data):
    result = data [:] """원본의 복사본을 만듬"""
    temp = data [2]
    data [2] = data [3]
    data [3] = temp
    return data

score = [1,2,3,4,5]
shuffled_score = shuffle0(score)
```



**TIP**

* 백 만개의 인자가 있는 큰 리스트를 복사하면 메모리을 많이 소비하기 때문에 그 것에 대해서도 생각해야 함. 
* 변수 이름을 의도가 잘 드러나는 이름으로 지어주는 것이 중요. 함수 : 함수가 하는 일
  * Python : Use uppercase - sort_by_length ()

case-sensitive language ex) Visual Basic

hash value : hash-based sampling



1. Using `random` package - .shuffle

   ```python
   import random
   
   data = [1,2,3,4,5]
   shuffled_list = random.shuffle
   print(shuffled_list)
   ```

   .sample

   ```python
   import random 
   
   data = [1,2,3,4,5]
   random.shuffle(data, 5) 
   --> random.shuffle(data, len(data))
   ```

   

2. `sort`to create a list

   ```py
   
   ```

3. 실제 세상으로부터 노이즈를 끌어와서 랜덤 요소로 쓰려는 시도

   ```python
   
   ```



## Shuffle Theories

Measure the performance of the shuffle algorithm : 

https://bost.ocks.org/mike/shuffle/compare.html

**A good shuffling algorithm is unbiased**; you should see a uniform grey matrix with only a bit of white noise. A bad algorithm will show streaks in the matrix, indicating an un­even distribution.



**Fisher-Yates Shuffle**

https://bost.ocks.org/mike/shuffle/



## Internet, Web, Web Browser and HTML

Thet Internet : 

 * inter-network of computer networks

   

Web/World Wide Web

- Computer network that communicates using HTTP (HyperText Transfer Protocol)



웹이 아닌 인터넷

- 게임, 카카오톡, 이메일
- 블루투스



웹에서 가장 중요한 개념:

* URL (Uniform Resource Locator):	

  * protocol://user@host:port/path?query#fragment

  * https://(username & port omitted)www.google.com/search?q=test

  * Hyperlink, Hypertext, HTML (HyperText Markup Langauge)

    

## Web Crawling

python code that imitates web browser to fetch data online

https://docs.python.org/3/library/urllib.html

```python
from urllib import request

url = "http://www.naver.com"
with request.urlopen(url) as f:
    # 'with 어쩌고 as 저쩌고' 구문은 '어쩌고'가 만든 자원을 '저쩌고'에 할당하고 
    # 다 쓴 다음에는 자원 사용을 해제하기 위해 쓰인다. 
	html = f.read().decode('utf-8')
	print(html)
```

```python
import urllib.request

url = "http://www.naver.com"
with urllib.request.urlopen(url) as f:
    html = f.read().decode('utf-8')
	print(html)
    
```

자원 관리 : 프로그래밍에서 중요 (메모리, CPU)

package module function call the function with paramter url that derives the result o f

python standard library 



`with...as` Syntax

```
Without the with statement, we would write something like this:
file = open("welcome.txt")

data = file.read()

print data

file.close()  # It's important to close the file when you're done with it
```

```
Opening a file using with is as simple as: with open(filename) as file:
with open("welcome.txt") as file: # Use file to refer to the file object

   data = file.read()

   do something with data

Opens output.txt in write mode
with open('output.txt', 'w') as file:  # Use file to refer to the file object

    file.write('Hi there!')
Notice, that we didn't have to write "file.close()". That will automatically be
called.
```



more explanation : https://docs.python.org/3/howto/urllib2.html

## 저작권(Copyright), 라이선스(License)

HTML DOM

CSS Selector



**저작권(copyright), 라이선스(License)**

* 만드는 코드, 파생된 데이터도 저작권을 가지고 있음

* 소프트웨어 저작권 & 데이터/콘텐츠 저작권으로 나뉨. (겹치는 부분도 있기는 함)

* 라이선스 모듈 : 창작자들이 쉽게 라이선스를 만들 수 있고 이용자들이 쉽게 라이선스를 알아볼 수 있음

  * CCL :https://creativecommons.org/
  * 공공누리 https://www.copyright.or.kr/gov/nuri/rule_info/index.do

* Robots.txt (Robots Exclusion Standard)

  * De Facto Standard (not an official industry standard but used conventionally)

  * ```html
    https://www.daum.net/robots.txt
    
    User-agent: *
    Disallow: /
    
    # For all user-agents, don't allow any crawling
    ```

    ```html
    https://www1.president.go.kr/robots.txt
    
    User-agent: *
    Disallow:
    
    # For all user-agents, allow all the crawling
    ```

    ```html
    https://www.nytimes.com/robots.txt
    
    User-agent: *
    Allow: /ads/public/
    Allow: /svc/news/v3/all/pshb.rss
    Disallow: /ads/
    Disallow: /adx/bin/
    Disallow: /archives/
    Disallow: /auth/
    Disallow: /cnet/
    Disallow: /college/
    Disallow: /external/
    Disallow: /financialtimes/
    Disallow: /idg/
    Disallow: /indexes/
    Disallow: /library/
    Disallow: /nytimes-partners/
    Disallow: /packages/flash/multimedia/TEMPLATES/
    Disallow: /pages/college/
    Disallow: /paidcontent/
    Disallow: /partners/
    Disallow: /register
    Disallow: /thestreet/
    Disallow: /svc
    Disallow: /video/embedded/*
    Disallow: /web-services/
    Disallow: /gst/travel/travsearch*
    Disallow: /1996/06/17/nyregion/guest-at-diplomat-s-party-accused-of-rape.html
    Disallow: /*.amp.html$
    
    User-agent: googlebot
    Allow: /*.amp.html$
    
    User-agent: bingbot
    Allow: /*.amp.html$
    
    User-Agent: omgilibot
    Disallow: /
    
    User-Agent: omgili
    Disallow: /
    
    Sitemap: http://spiderbites.nytimes.com/sitemaps/www.nytimes.com/sitemap.xml.gz
    Sitemap: http://www.nytimes.com/sitemaps/sitemap_news/sitemap.xml.gz
    Sitemap: http://spiderbites.nytimes.com/sitemaps/sitemap_video/sitemap.xml.gz
    Sitemap: http://spiderbites.nytimes.com/sitemaps/www.nytimes.com_realestate/sitemap.xml.gz
    Sitemap: http://spiderbites.nytimes.com/sitemaps/www.nytimes.com/2016_election_sitemap.xml.gz
    
    # complicated
    ```

* Rate limits & Firewall

  * ex) To help prevent strain on Trello's servers, our API imposes *rate limits*per API key for all issued tokens
  * a **firewall** is a [network security](https://en.wikipedia.org/wiki/Network_security) system that [monitors](https://en.wikipedia.org/wiki/Network_monitoring) and controls incoming and outgoing [network traffic](https://en.wikipedia.org/wiki/Network_traffic) based on predetermined security rules.[[1\]](https://en.wikipedia.org/wiki/Firewall_(computing)#cite_note-1) A firewall typically establishes a barrier between a trusted internal network and untrusted external network, such as the [Internet](https://en.wikipedia.org/wiki/Internet).



## Markup Language

* 마크업 : 기존 문서에 기입하는 부가적인 정보

* 마크업 언어 : 마크업 정보를 컴퓨터로 일관되기 표기하기 위한 인공 언어. 

  * ex) Markdown : The language of this _document_, the lightweight markup language

  * 컴퓨터 : 인간처럼 맥락을 모른다. 하나하나 일일히 지시해야 함. 컴퓨터에게 지시할때 모호성이 있으면 안됨. 명확한 규칙이 필요함. 

  * Major Dilemma : 마크업에 들어가는 기호가 본문에 나오면 어떻게 할것인지?

  * 엔터를 두번 쳐야 끝남. 

    http://markdownlivepreview.com/

* HTML (HyperText Markup Language)  : standard markup language for creating web pages and web applications  (HyperText : Documents that contain hyperlinks)

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  	<meta charset="utf-8"> # head tag뒤에 넣는 것이 좋음. meta 정보 없으면 대충 알아맞추는데 그 것이 맞지 않으면 이상하게 페이지가 뜸. 뙭뵑이런 식으로 
  
  <title>'돌아온' 오늘 MBC 뉴스의 첫 앵커 멘트는 '사과'였다 </title>
  </head>
  
  <body>
  <p> 2017년 12월 08일 15시 27분, <a href="https://www.google.com"> 허완 기자</a>, 허핑턴포스트코리아 </p>
  
  <blockquote> # 들여쓰기는 사람의 편의를 위한 것임. 
  	<p> “저희 MBC는 &lt;신임 &lt 최승호 사장의 취임에 맞춰, 오늘(8일)부터 뉴스데스크 앵커를 교체하고 당분간 뉴스를 임시체제로 진행합니다. 저희들은 재정비 기간 동안 MBC 보도가 시청자 여러분께 남긴 상처들을 거듭 되새기며, 철저히 반성하는 시간을 갖겠습니다.</p>
  	<p> 치밀한 준비를 거쳐 빠른 시일 안에 정확하고 겸손하고 따뜻한 뉴스데스크로 시청자 여러분께 다시 인사드리겠습니다."</p>
  </blockquote>
  
  <p> 8일 저녁 8시, MBC 메인뉴스인 '뉴스데스크' 대신 'MBC뉴스'라는 타이틀로 방송된 뉴스에서 임시 앵커를 맡은 김수지 아나운서는 짤막한 사과문을 읽어내려갔다.</p>
  </body>
  </html>
  ```

  <html> : `tag`  

  html element : 여는 태그와 닫는 태그 사이의 전체. "children"이라고도 함. 

  구조를 그리면 '나무'가 나옴. 

https://ko.khanacademy.org/computing/computer-science/algorithms/recursive-algorithms/a/recursion

## HTML DOM (Document Object Model) tree

When an HTML document is loaded into a web browser, it becomes a document object.

The document object is the root node of the HTML document.



외부 라이브러리(html5lib)를 설치해서 생성.

```python
pip install html5lib # Install library

```

https://colab.research.google.com/drive/1mxTcw4ENadBzCB5x7aw3RP4DjWzJJuaH#scrollTo=FrAw2RAe4rTv



파싱이 되지 않을때?** 

사이트가 망가졌을 수도 있음. 

체크 --> https://validator.w3.org/nu/?doc=https%3A%2F%2Fwww.naver.com%2F



**Attributes**

.()

() -> attributes - variable & function

dir.(object) --> find attributes

Without arguments, return the list of names in the current local scope. With an argument, attempt to return a list of valid attributes for that object.

https://docs.python.org/2/library/functions.html



None vs none