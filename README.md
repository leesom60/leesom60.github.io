## **How to bulid?**
--- 

### 1. repository 생성
---
- [leesom60](https://leesom60.github.io/) 원격 저장소를 생성하였습니다. 
- 'webProject' 로컬 저장소를 만들고 원격 저장소를 clone하였습니다.  
  

### 2. 첫 markdown file 작성
---
- git에 관해 설명하는 post를 게시하고자 git.md 파일을 [dillinger.io](dillinger.io)로 작성하였습니다. 
    - 모든 md 파일은 [dillinger.io](dillinger.io)로 작성하였습니다. 

### 3. Jekyll 설치
---
``` jekyll new . --force``` 명령어로 로컬 저장소에 jekyll을 설치하였습니다.

### 4. git.md post
---
1) 이전에 만든 git.md를 _posts 디렉토리로 이동하였습니다 
2) 이를 add, commit, push하여 post하였습니다.

### 5. 2개의 post 생성
---
jekyll과 markdown에 대해 설명하는 추가적인 2개의 markdown 파일을 작성하고 post하였습니다.

### 6. 테마 적용
---
[jekyllthemes.org](http://jekyllthemes.org/)에서 'YAT THEME'를 선택하였습니다.
> [해당 테마를 사용할 수 있는 github link](https://github.com/jeffreytse/jekyll-theme-yat/)  

1. YAT 테마를 ```git clone```하여 로컬 저장소에 받아왔습니다.
2. _posts 디렉토리를 제외한 모든 파일과 디렉토리들을 로컬저장소에 덮어썼습니다.

### 7. _config.yml 수정
---
원래 초반에 해야 했었던 작업이었지만 잊어버려서 테마를 적용한 후 _config.yml 파일을 수정했습니다. 

### 8. comments 기능 구현 시도
---
1. disqus에 가입하고 
2. disqus 사이트를 생성하고
3. _config.yml과 post.html, _posts/*.md 파일에 disqus를 반영하였으나

> We were unable to load Disqus. If you are a moderator please see our troubleshooting guide.

라는 error가 발생하며 댓글 기능을 구현할 수 없었습니다. 

문제가 무엇인지 알아보기 위해 구글링을 하였더니 
**Disqus를 사용 중인 사이트를 "Trusted Domain(신뢰할 수 있는 도메인)"으로 등록**
하라는 해결책이 일반적이었습니다.

그러나 이를 적용함에도 불구하고 erro는 계속 발생하였습니다.

### 9. favicon 적용
---
1. [www.flaticon.com](https://www.flaticon.com/) 사이트에서 ![대체 텍스트](https://cdn-icons-png.flaticon.com/512/49/49046.png) 
위의 이미지를 선정하였습니다.

2. [www.favicon-generator.org](https://www.favicon-generator.org/) 사이트에서 위의 이미지를 favicon으로 변환하였습니다.
3. 변환한 파일의 압축을 풀고 파일의 이름을 ```favicon.ico```로 바꾼 후 assets/ 디렉토리 밑으로 이동하였습니다.
4. ```_includes/head/custom-head.html``` 경로의 파일을 수정해준 후 원격 저장소에 업로드하였습니다.

### 10. comments 구현 완료
---

> **문제점 1**

```_config.yml``` 파일의 url 부분에 ```https://leesom60.github.io```가 들어가야 하는데 ""로 비어 있었습니다.

> **문제점 2**

yat theme의 파일을 덮어쓴 후 disqus 댓글 설정하는 부분에
```
disqus:
shortname: 
```
만 적혀져 있었기 때문에 그 부분만 구현했습니다. 그러나 정상적으로 동작하게 하려면
```
comments:
    provider: "disqus"
    disqus:
    shortname: "blog-with-git"
```
이렇게 구현해야 합니다.

두 문제점을 해결하니 comments가 정상적으로 구현되었습니다.
