## Selenium이란?

웹앱을 테스트하는데 이용하는 프레임워크다.webdriver라는 API를통해 운영체제에 설치된 Chrome등의 브라우저를 제어하게 된다.

브라우저를 직접 동작시킨다는 것은 JavaScript를 이용해 비동기적으로 혹은 뒤늦게 불러와지는 컨텐츠들을 가져올 수 있다는 것이다.즉, '눈에 보이는' 컨텐츠라면 모두 가져올 수 있다는 뜻이다.Selenium은 실제 웹 브라우저가 동작하기 때문에 JS로 렌더링이 완료된 후의 DOM결과물에 접근이 가능하다.

```python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys


driver = webdriver.Chrome('./chromedriver')
url = 'https://google.com'
driver.get(url

driver.find_element_by_css_selector('.gLFyf.gsfi').send_keys('파이썬') # 검색창이 갖고 있는 클래스로 접근하고 파이썬을 검색
driver.find_element_by_css_selector('.gLFyf.gsfi').send_keys(Keys.ENTER) # 파이썬 검색 후 엔터키를 누름
driver.find_element_by_css_selector('.LC20lb').click() # 검색 후 나온 결과중에서 클래스로 접근해 클릭하는 명령
driver.find_elements_by_css_selector('.LC20lb')[2].click() # 검색 후 나온 결과중에서 list의 3번째를 입력함 이때 주의할 점은 복수인지 단수인지 잘 봐야 함

           
```