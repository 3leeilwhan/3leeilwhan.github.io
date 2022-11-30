## Github에서 테마 다운 받기  

- 노션에 나와있는 링크에서 마음에 드는 테마를 몇 개 골라 다운받았는데 `jekyll`을 실행하는데 계속 에러가 나와 수업시간에 다룬 `Lanyon` 테마를 다운받아 사용하였다.


- #### Lanyon  
     Lanyon is an unassuming [Jekyll](http://jekyllrb.com) theme that places content first by tucking away navigation in a hidden drawer. It's based on [Poole](http://getpoole.com), the Jekyll butler.

![Lanyon](https://f.cloud.github.com/assets/98681/1825266/be03f014-71b0-11e3-9539-876e61530e24.png)
![Lanyon with open sidebar](https://f.cloud.github.com/assets/98681/1825267/be04a914-71b0-11e3-966f-8afe9894c729.png)  




```
git clone https://3leeilwhan.github.io.git '새 폴더 이름' 
```  

- 위 코드를 이용하여 원격저장소에 있는 `repository`를 나의 로컬 저장소로 불러왔다.  


- `Lanyon` 테마를 사용하는 데 필요한 파일들을 로컬 저장소에 넣어놨다.  

```
bundle exec jekyll serve
```  
- 위 명령어를 사용하여 서버를 실행하였다.

- 하지만 4000번 포트에서 이미 실행되어 있는 것이 있어, 그것을 kill한 후 위 명령어를 다시 사용하여 서버를 실행하였다.  

## 테마에서 개인 정보 수정  
- \_config.yml 파일을 수정하였다.  
  `title`, `email`, `description`, `username` 등 여러 정보를 수정하였다.  
  
## post 작성  
- \_posts 디렉토리 안에 post 내용을 `markdown`파일로 저장하였다.  
- 나의 프로필, git, github, jekyll, markdown에 대한 내용을 post에 담았다.  
- post에 지금까지 배운 내용을 담으며 3주간 수업시간에 배운 정보들을 되짚어 보는 계기가 되었다.  

## 올린 각각의 post마다 댓글 기능 추가하기  
- [https://disqus.com](https://disqus.com)에 접속하였다.  
- Signup을 눌러 회원가입을 하였다.  
- "I want to install Disqus on my site"를 선택하고 나의 블로그의 정보를 입력한 후 Platform 중 Jekyll을 선택하였다.  

```
comment:  
  provider:       "disqus"  
  disqus:
    shortname:    "이름"
    
```
- \_config.yml 파일에 위의 코드를 추가하였다.  
- disqus 홈페이지에서 Universal Code를 복사하고 페이지에 맞게 수정하였다.  
- \_layouts/post.html 파일에 다음의 주석을 해제 후, PAGE_URL과 PAGE_IDENTIFIER를 설정하였다.

```
let PAGE_URL = "{{site.url}}{{page.url}}"
let PAGE_IDENTIFIER = "{{page.url}}"
```  

- post의 초기 설정 값에 "comments:true"를 추가하였다.  

## Google Analytics 이용  

- `data stream` 항목에서 내 블로그 사이트를 등록하였다.  
- \_includes 폴더에 analytics.html 파일을 새로 만들고, 다음 코드를 입력하였다.  

```
<script async src="https://www.googletagmanager.com/gtag/js?id=측정ID"></script>
<script>
window.dataLayer = window.dataLayer || [];
function gtag(){dataLayer.push(arguments);}
gtag('js', new Date());

gtag('config', '{{ site.analytics-google }}');
</script>
```

- default.html의 head 태그에 다음의 코드를 추가한다.  
```
{% raw %} {% include analytics.html %} {% endraw %}
```









  

 




