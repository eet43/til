# selenium 라이브러리란 ?

python 서버에서는 대표적으로 requests 라이브러리를 사용하여 프론트와 통신한다.<br><br>

그러나 requests 라이브러리는 처음에 html 이 정적으로 내려진 데이터만 스크래핑 요청할 수 있다.<br><br>

즉 html 이 브라우저에 받아진 상태에서 다시 ajax 를 통해 데이터를 받아와 동적으로 출력해주는 사이트에서는, 실시간 데이터를 받을 수 없다는 의미이다.<br><br>

이건 selenium 라이브러리를 통해 해결할 수 있다.<br><br>

## 어떻게 ?

브라우저를 드라이버를 통해 직접 띄운 후 소스코드를 가져오는 방법이다.<br><br>

``` python

driver = webdriver.Chrome('./chromedriver')  # 드라이버를 실행합니다. 드라이버는 따로 버전에 맞게 다운받아야한다.


url = "https://www.melon.com/chart/day/index.htm" # 크롤링 할 주소
# headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64)AppleWebKit/537.36 (KHTML, like Gecko) Chrome/73.0.3683.86 Safari/537.36'}
# data = requests.get(url, headers=headers)

driver.get(url)  # 드라이버에 해당 url의 웹페이지를 띄운다. 실제 브라우저가 실행된다.
sleep(5)  # 페이지가 로딩되는 동안 5초 간 기다립니다. 

req = driver.page_source  # html 소스코드를 가져옵니다.
driver.quit()  # 정보를 가져왔으므로 드라이버는 꺼줍니다.

soup = BeautifulSoup(req, 'html.parser')  # 가져온 정보를 beautifulsoup으로 파싱해준다.

songs = soup.select("#frm > div > table > tbody > tr")
print(len(songs))

for song in songs:
    title = song.select_one("td > div > div.wrap_song_info > div.rank01 > span > a").text
    artist = song.select_one("td > div > div.wrap_song_info > div.rank02 > span > a").text
    likes = song.select_one("td > div > button.like > span.cnt").text
    print(title, artist, likes)
```
