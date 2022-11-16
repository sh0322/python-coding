```python
%pip install requests  beautifulsoup4 openpyxl lxml
```

    Requirement already satisfied: requests in c:\anaconda\lib\site-packages (2.27.1)
    Requirement already satisfied: beautifulsoup4 in c:\anaconda\lib\site-packages (4.11.1)
    Requirement already satisfied: openpyxl in c:\anaconda\lib\site-packages (3.0.9)
    Requirement already satisfied: lxml in c:\anaconda\lib\site-packages (4.8.0)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\anaconda\lib\site-packages (from requests) (1.26.9)
    Requirement already satisfied: charset-normalizer~=2.0.0 in c:\anaconda\lib\site-packages (from requests) (2.0.4)
    Requirement already satisfied: idna<4,>=2.5 in c:\anaconda\lib\site-packages (from requests) (3.3)
    Requirement already satisfied: certifi>=2017.4.17 in c:\anaconda\lib\site-packages (from requests) (2021.10.8)
    Requirement already satisfied: soupsieve>1.2 in c:\anaconda\lib\site-packages (from beautifulsoup4) (2.3.1)
    Requirement already satisfied: et-xmlfile in c:\anaconda\lib\site-packages (from openpyxl) (1.1.0)
    Note: you may need to restart the kernel to use updated packages.
    


```python
import requests
from bs4 import BeautifulSoup

url = "https://search.daum.net/search?w=tot&DA=YZR&t__nil_searchbox=btn&sug=&sugo=&sq=&o=&q=%EB%8C%80%EA%B5%AC+%EB%82%A0%EC%94%A8"
res = requests.get(url)


soup = BeautifulSoup(res.text, "lxml")
#print(soup.title)
#print(soup.title.get_text())
#print(soup.div)
print(soup.find(attrs = {"class":"txt_temp"}))



```

    <strong class="txt_temp">10<span class="txt_unit">℃</span></strong>
    


```python
import requests
from bs4 import BeautifulSoup

name = {"북문","정문","동문"} #url 수정을 위한 맛집 이름 리스트
for store in name:
    url = "https://search.daum.net/search?nil_suggest=btn&w=tot&DA=SBC&q=%EA%B2%BD%EB%B6%81%EB%8C%80+{}+%EB%A7%9B%EC%A7%91".format(store)
    res = requests.get(url)
    soup = BeautifulSoup(res.text, "lxml") #구문을 분석하기위한 파서
    
    img = soup.find_all("img",attrs={"class":"thumb_img"}) #이미지 태그 가져오기
    
    for idx,image in enumerate(img): #enumerate를 사용하면 똑같이 for문을 도는데 idx가 0~ 4로 증가
        img_url = image["src"] #이미지 소스 저장
        
        if img_url.startswith("//"): #다음이미지를 접근하기 위해  https 붙이기
            img_url = "https:" + img_url
            
        image_res = requests.get(img_url) #이미지를 파일로 저장하기 위해 다시 접속하기

        with open("food_{}_{}.jpg".format(store,idx+1),"wb") as f:
            f.write(image_res.content )

        if idx == 4: #상위 5개의 이미지만 저장하기 위해서
            break
```


```python
pwd
```




    'C:\\Users\\박세현'


