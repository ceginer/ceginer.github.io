---
layout: post
title: First Post!
---

# 피로그래밍 배운 것 복습

# 1. Javascript

### 1. javascript의 DOM조정

- 웹에서 DOM 이란 Document object model , 즉 웹에서 html의 각 부분을 객체로써 표한한 것
- javascript의 DOM 을 조정해 여러가지 event를 만들 수 있다 →
    
    (window의 document 를 이용한 document.SelectQuery와 같이 사용)
    

[Document](https://choiteemo.pythonanywhere.com/practice)

### 2. javascript - vanilla javascript

- 순수하게 javascript 로만 이루어진 코드
- vanilla javascript 로 캘린더 만들기 →
    
    [캘린더 만들기 - 설명ver](https://www.notion.so/ver-7ae66df27df2471f92ae16e6fae1c0ab)
    

### 3. AJAX - Asynchronous Javascript And Xml

- 비동기식 자바스크립트
    - 이름에 XML 들어가지만 크고 무거운 XML 대신 요즘에는 모두 json으로 쓰는 추세
- **csr 방식과 AJAX / AJAX 와 페이지 렌더링**
    
    ### [ ajax와 페이지 랜더링 ]
    
    ---
    
    - **Reference_1** →  **AJAX란? -** [https://tibetsandfox.tistory.com/15](https://tibetsandfox.tistory.com/15)
    - **Reference_2** → **CSR** vs **SSR -** [https://velog.io/@commitnpush/CSR-vs-SSR](https://velog.io/@commitnpush/CSR-vs-SSR)
    
    **AJAX 가 나오기 전 페이지** → ‘submit’과 같은 새로운 정보 = 새로운 웹페이지
    
    이유? → HTTP 프로토콜이 서버의 request 요청에 대한 response 를 받은 이후 수신을 중단함.
    
    **AJAX** → 
    
    - 페이지 뼈대만 랜더링
    - 요청 시 웹앱에 필요한 대부분의 JS파일, CSS파일들을 서버로부터 응답받음
        
        ( = 필요한 데이터는 XMLHttpRequest (자바스크립트) 로 서버에 요청함 ), 
        
    - 서버는 requests를 받아 XML or JSON 형식으로 데이터 응답
    - 페이지 갱신
    
    ### [ AJAX 즉, csr 방식의 단점 ]
    
    ---
    
    1. **초기 로딩속도가 느리다.**
    - 처음 요청 시 웹앱에 필요한 대부분의 JS파일 CSS파일들을 서버로부터 응답받아야 하며 이를 화면에 표시하기 위해서 브라우저가 열심히 작업을 수행해야 하기 때문이다. 
    뿐만아니라 웹앱의 규모가 크고 사용자PC의 사양이 높지 못하다면 기존 방식인 서버에서 직접 페이지를 렌더링하는 SSR 방식이 오히려 빠를 수도 있다
    
    → 하지만 user들은 동적으로 변화되는 페이지에서 더 빠른 페이지를 경험할 수 있음.
    
    1. **검색엔진 최적화(SEO, Search Engine Optimization)에 불리**
    - CSR은 초기 요청에는 뼈대에 해당하는 페이지밖에 응답이 안 되고 JS가 동작 하면서 내용이 채워지는 방식인데 구글 검색엔진을 제외한 검색엔진은 페이지에 포함된 자바스크립트를 실행하여 완성된 결과화면을 인덱싱하지 않는다.
    
    → 구글 크롤러는 js도 해석한다 한다, 하지만 완벽한 것은 아니기에 csr 방식의 단점이라 할 수 있음.
    

# 2. Django

## 1. what is django?

- django 는 mvc(model, view, controller) 가 아닌 mtv(mode, templates, view) 형식
    - 디자인 패턴 - **효율적으로 코드를 작성하기 위한 코딩 규칙 or 프로젝트 구조** ( mvc, mtv, mvp, mvvm )
    - model - DB를 다루는 곳으로써 원래는 sql 다루지만 django는 ORM 기술로 class로 대체 가능
    - templates- 유저에게 보여지는 화면 (html, css 로 구성)
    - MVC 패턴의 컨트롤러에 대응
        - 사진
            
            ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled.png)
            
    - **REFER** - [https://tibetsandfox.tistory.com/16](https://tibetsandfox.tistory.com/16)

![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%201.png)

😎

이해되나용?

→>>>>> 그래서!

<aside>
💡 보통 장고 프로젝트를 할때는 Model- Url- view- template 순으로 코딩하는 것을 추천합니다!

</aside>

## 2. Start Django

1. **venv 가상환경 설치**
2. **project 생성**

```python
(venv) $ django-admin startproject (프로젝트이름)

ex)
(venv) $ django-admin startproject config 

```

→ 이런 식으로 하면 project 안에 같은 이름의 폴더가 하나 더 생기므로 빼내줘야 함.

귀찮다면 `$ django-admin startproject userproject .`  식으로 . 을 붙여주기

1. **필요하다면 app 생성**

```bash
(venv) $ python3 manage.py startapp (앱이름)

ex) market라는 app 생성
-> (venv) $ python3 manage.py startapp market
```

- **💡 App & project 차이점**
    
    ### Project vs App
    
    장고에서 웹 서비스의 각각 기능은 앱 단위로 구현합니다. 서로 다른 기능을 하는 앱을 여러 개 모아서 하나의 프로젝트로 만드는 것입니다. 실제로 하나의 프로젝트는 여러 개의 앱과 약간의 설정 파일들로 구성되어 있습니다. (출처 14기 김영빈님)
    
    project
    
    - 웹 서비스의 전체 <쇼핑몰>
    
    app
    
    - 그 서비스 안에서 하나하나의 기능을 나타내는 단위 <회원가입, 장바구니 ..>
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%202.png)
    
    **프로젝트와 앱을 연결하기**
    
    《pirogramming16/settings.py》를 열어서 아래와 같이 INSTALLED APP에 앱 이름을 추가합니다
    

1. **project, app 연결 -** config/urls.py에 코드를 추가하기

```python
from django.urls import path,include
from django.contrib import admin
from django.urls import path
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('market.urls')),
]
```

- `config.urls` 추가
    
    ```python
    path('', include('posts.urls')),
    ```
    
- `posts.urls` 생성
    
    ```python
    from django.urls import path 
    
    from . import views
    
    app_name = "posts"
    
    urlpatterns = [
    
    ]
    ```
    

1. **django 모델 설정**
- 모델 추가
    
    ```python
    class Post(models.Model):
        title = models.CharField(max_length= 100, verbose_name="제목")
        user = models.CharField(max_length= 50, verbose_name="유저이름")
        content = models.TextField(verbose_name="내용")
        region = models.CharField(max_length=50, verbose_name="지역")
    		price = models.IntegerField(verbose_name="가격")
        created_at = models.DateTimeField(auto_now_add=True)
        updated_at = models.DateTimeField(auto_now=True)
    ```
    
- 장고 [settings.py](http://settings.py) 수정
    - TIME_ZONE = “Asia/Seoul”
    - LANGUAGE_CODE = “ko”
    1. 
- 마이그레이션 설정
    
    마이그레이션 파일은 디비에게 요구할 명세서(주문서)를 만드는 것과 같다 
    
    ```python
    python manage.py makemigrations {앱 이름} 
    
    ex)
    python [manage.py](http://manage.py) makemigrations posts
    
    ```
    
    마이그레이트는 `makemigration`으로 만들어진 명세서를 디비에 전달하는 행위이다.
    
    ```python
    python maange.py migrate {앱 이름}
    
    ex)
    python [manage.py](http://manage.py) migrate posts 
    ```
    
- 어드민 페이지
    
    python [manage.py](http://manage.py) migrate : 장고 기본 모델링 적용 
    
    python [manage.py](http://manage.py) createsuperuser 
    
    [`http://127.0.0.1:8000](http://127.0.0.1:8000/)/admin` 으로 들어가보자 
    
    ```python
    #[posts.admin.py](http://posts.admin.py) 
    
    from .models import Post
    
    @admin.register(Post)
    class PostAdmin(admin.ModelAdmin):
        pass
    ```
    

## 3. 본격적인 CRUD 만들기

- Create, Read, Update, Delete 기능

- 이후 본격적인 내용은 `[피로그래밍 17] CRUD 기초` 를 그대로 참고하였음.
    
    # CRUD
    
    > 데이터 처리를 위한 필수적인 요소
    > 
    - C reate (생성)
    - R ead (읽기)
    - U pdate (수정)
    - D elete (삭제)
    
    <aside>
    💡 왜? 중요한가??  모든 서비스는 `CRUD`로 설명할 수 있다!
    
    </aside>
    
    - 예시
        
        
        ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled.jpeg)
        
        ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%201.jpeg)
        
        ![KakaoTalk_Photo_2022-07-14-01-11-16 003.jpeg](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/KakaoTalk_Photo_2022-07-14-01-11-16_003.jpeg)
        
        ### 피로그래밍
        
        Create: 피드 생성, 스토리 생성, 댓글 달기
        
        Read: 피드, 스토리 보기
        
        Update: 피드 변경 
        
        Delete: 피드 삭제, 스토리 삭제
        
        ### 당근 마켓
        
        Create: 내 물건 팔기, 게시판에서 글 쓰기
        
        Read: 물건 보기, 광고 보기
        
        Update: 가격 수정 
        
        Delete: 내 물건 게시물 삭제
        
        ### 유튜브
        
        Create: 동영상 업로드, 댓글 달기
        
        Read: 영상 시청 
        
        Update: 썸네일 변경, 영상 제목 변경 등등
        
        Delete: 영상 삭제, 댓글 삭제 
        
    
    ## Read
    
    ### 장고 내용 읽어보기
    
    ```python
    #posts.views 
    from .models import Post
    
    def home(request):
    	posts = Post.objects.all()
    	print(posts)
    ```
    
    ### 홈 화면 페이지 템플릿 작성
    
    ```html
    <!DOCTYPE html>
    <html lang="ko">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>홈 화면</title>
    </head>
    <body>
        {% for post in posts %}
            <article>
                <h1>
                       {{post.title}}
                </h1>
                <p>
                    {{post.region}}
                    {{post.user}}
                </p>
                <p>
                    {{post.price}} 원
                </p>
                <p>
                    {{post.content}}
                </p>
            </article>
        {% endfor %}
    </body>
    </html>
    ```
    
    ---
    
    ## Create
    
    게시글 업로드 화면 작성 
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>게시글 올리기</title>
    </head>
    <body>
       <form action="/create" method="get">
            <h2>
                <input type="text" name="title" placeholder="제목">
            </h2>
            <p>
                <input type="text" name="user" placeholder="유저">
                <input type="text" name="region" placeholder="지역">
                <input type="number" name="price" placeholder="가격">
            </p>
            <textarea name="content" id="" cols="30" rows="10"></textarea> 
            
            <div>
                <input type="submit" value="제출">
            </div>
       </form>
    </body>
    </html>
    
    ```
    
    ### Request method 의미?
    
    `get`:  기존 데이터를 읽어 올 때 쓰임
    
    `post`: 새로운 데이터를 생성하거나, 기존 데이터를 수정하거나, 삭제할 때 쓰임 
    
    - POST 요청 확인하기
        
        ```python
        if request.method == 'POST':
                print(request.POST)
        ```
        
    
    ### 데이터 베이스에 잘 들어갔는지 확인하기
    
    ```python
    if request.method == 'POST':
            # post 요청 값 받기 
            title = request.POST["title"]
            user = request.POST["user"]
            region = request.POST["region"]
            content = request.POST["content"]
    				price = request.POST["price"]
    
            # 데이터 베이스에 저장하기 
            Post.objects.create(title=title, user=user, region=region, content=content)
    
            print(Post.objects.all())
    ```
    
    ### 홈 화면으로 redirect
    
    ```python
    from django.shortcuts import redirect
    
    redirect("{url 주소"})
    
    redirect('/')
    ```
    
    `redirect` : 장고에서 제공하는 단축키 
    
    ### 작성 화면과 메인 화면 이동하기 위한 a 태그 추가
    
    ```html
    "home.html"
    <a href="/">Home</a>
    
    "create_post.html"
    <a href="/new">create</a>
    ```
    
    ---
    
    ## Update
    
    ### DB 내가 설정하지 않은 id 값?
    
    `id`  는 unique → 중복되지 않는 값. 장고에서 알아서 세팅해준다. 
    
    ### 디테일 페이지 만들기
    
    request 요청대로 만들어보자. 일단 경로 설정부터!
    
    ### detail.html
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>상세화면</title>
    </head>
    <body>
        <article>
            <h2>
                제목 : {{ post.title }}
            </h2>
            <p>
                작성자: {{ post.user }}
                지역: {{post.region}}
            </p>
    				<p>
                {{post.price}} 원
            </p>
            <div>
                {{post.content}}
            </div>
        </article>
    
        <div>
            업데이트 : <a href="/update/{{post.id}}">update</a>
        </div>
    		<div>
            홈 화면으로 가기: <a href="/">Home</a>
        </div>
    </body>
    </html>
    ```
    
    ### update 화면 구성하기
    
    `create` 화면과 똑같다. 
    
    기존 데이터를 담고 있어야 한다 → GET 요청
    
    ### update 경로부터 설정
    
    ### update.html
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>게시글 올리기</title>
    </head>
    <body>
       <form action="/update/{{post.id}}" method="post">
        <!-- {% csrf_token %} -->
            <h2>
                <input type="text" name="title" placeholder="제목" value="{{post.title}}">
            </h2>
            <p>
                <input type="text" name="user" placeholder="유저" value="{{post.user}}">
                <input type="text" name="region" placeholder="지역" value="{{post.region}}">
    						<input type="number" name="price" placeholder="가격" value="{{post.price}}">
            </p>
            <textarea name="content" id="" cols="30" rows="10">{{post.content}}</textarea> 
            
            <div>
                <input type="submit" value="제출">
            </div>
       </form>
       <a href="/">Home</a>
    </body>
    </html> 
    ```
    
    ---
    
    ## Delete
    
    ---
    
    # 🎁 보너스
    
    ## 장고만 url 연결하기
    
    왜? 
    
    - 구체적인 url 주소가 자주 바뀌어도 name으로 맵핑되기 때문에 대규모 수정할일 없어
    - 가독성에 좋음
    
    사용방법
    
    [posts.urls.py](http://posts.urls.py) 에서 아래 내용 추가
    
    ```python
    app_name = 'posts'
    ```
    
    ```html
    <a href = "{% url '앱_네임:네임' view_파라미터 %}">예시</a>
    
    or 
    
    <form action="{% url '앱_네임:네임' view_파라미터 %}" method="post">
    ```
    
    ## 동네 이름으로 검색하기
    
    ### home.html에 추가
    
    ```html
    <form action="{% url 'posts:home' %}" method="GET">
            동네로 검색하기 : <input type="search" name='query' placeholder="동네 이름을 검색해보세요!">
            <input type="submit" value="검색">
    </form>
    ```
    
    url 주소 확인 → path 로 들어오는 request 요청 순서 명시 
    
    home 화면에 로직 추가 
    
    ```python
    def home(request):
        query = request.GET.get('query', None)
        if query:
            posts = Post.objects.filter(region__contains=query)
        else:
            posts = Post.objects.all()
    
        context = {"posts": posts}
    
        return render(request, template_name="posts/home.html", context=context)
    ```
    
    여기서 request.GET.get() 은 무엇인가?? → [https://velog.io/@kimkrh/Django-request.GET.get](https://velog.io/@kimkrh/Django-request.GET.get)
    
    - request.get() → 파이썬 문법, 사전형 객체일 때 사용가능, return 없으면 None 반환
    - request.GET → django 문법, 받은 데이터를 사전형으로 바꿈
    - request.GET.get() → django 문법, 받은 데이터를 사전형으로 바꿔서 얻기, 없는 데이터는 None 반환

## 4. django DataBase 관리 - [models.py](http://models.py) (약간 커리큘럼 번외?)

- **Reference** - [https://eunjin3786.tistory.com/126](https://eunjin3786.tistory.com/126)

### [ 장고의 ORM ]

---

- 장고는 DB에 대한 관리를 **ORM**(object-relational-mapping) 방식으로 운영함 (= [`models.py`](http://models.py) )
    - 여기서 mapping이란  키(key) 역할을 하는 데이터와 값(value) 역할을 하는 데이터를 짝 지어(=연결 지어) 저장하는 데이터 구조 를 가리킨다.
    - 즉 ORM 이란 **객체와 DB를 관계적으로 연결지어** 준다는 뜻
- **Model**
    - 장고의 모델은 테이블에, 필드는 칼럼에 매핑되어짐.
        - 테이블? 칼럼(열) , 그게 뭐야???
            
            ### 테이블, column, field?
            
            ---
            
            ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%203.png)
            
            - **Table** 은 전체 엑셀 워크시트와 비슷함
            - **row** 는 어떠한 Class 에서 객체1(인스턴스1), 객체2, 객체3 … 와 같은 개념 
            (= record(어떤 레코드) , tuple( 셀 수 있는 수량의 순서 있는 열거 = 객체1, 객체2…)
            - **cloumn** 은  어떠한 속성값, 즉 도시, 이름, 나이, 주소 등과 같은 데이터의 분류할 수 있는 기준  ( = field , attribute(속성) )
            
            ### 그럼 말이 왜 달라?
            
            ---
            
            ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%204.png)
            
            **파일시스템** 은 최초의 형태 , 요구사항에 맞는 응용 프로그램을 하나하나 작성해 놓은 것.
            **DB 모델링**은 원하는 개념을 실상화 하는 것/ 
            **관계형 데이터베이스**는 파일시스템 형태의 DB 를 발전시켜 좀 더 일반적이게 만든 것, 
            
            → 이를 위해서 후에 우리가 ERD ( Entity-Relationship Diagram ) 을 만들게 되는 것임
            [ **이미지 refer -** [https://dana-study-log.tistory.com/entry/DB-데이터베이스-기초](https://dana-study-log.tistory.com/entry/DB-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EA%B8%B0%EC%B4%88) ]
            
            → 엥? 그러면 파일 시스템은 왜, 언제 써?
            
            - 각각의 장단점이 있대,
                - 파일시스템 단점 - [https://luv-n-interest.tistory.com/555](https://luv-n-interest.tistory.com/555)
                - 각각의 장단점 - (결국은 싼게 장땡이다….?)
                
                ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%205.png)
                
            - 운영체제를 다룰 때 주로 파일 시스템, 이외에는 관계형 DB (RDB) 사용
            
    
    → 즉, **파일 시스템  ⇒ 관계형 DB** 형식으로 바뀐것 ( Model(file) → Table , Filed → Column )
    

<aside>
🖥️ **장고는 [Models.py](http://Models.py) 를 이용하여 DB 를 관리하고, 장고 ORM은 객체와 DB를 연결시켜는 방식으로써 파일 시스템 형식의 장고 모델과 필드를 관계형 DB 형식의 테이블과 칼럼에 매핑 시켜 DB를 관리할 수 있게 한다.**

</aside>

### [장고는 모델을 만들 때 id를 기본적으로 만들어줌] + [**verbose_name=””, related_name=””]**

---

- **verbose_name , related_name**
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%206.png)
    
    verbose_name 이란? → `Qestion.date published` 으로 사용
    
    verbose_name은 human-readable한(사람이 읽기 좋은) 필드 네임이라고 합니다.
    
    verbose_name을 안 넘겨주면 장고는 클래스안에 정의한 field의 이름과 똑같이verbose_name을 만들어준다고 하네요. (만약에 verbose_name을 지정 안해줬으면 pub_date가 verbose_name이 되는 것입니다)
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%207.png)
    
    related_name → 역참조할 때 사용 
    
    Foreign key의 경우는 `self.playlist_a = Playlist.objects.create(title='Test1 Playlist', video=self.video_a)` 한 뒤에, 하면 참조 됨.
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%208.png)
    
    ---
    
    하지만 역참조는 
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%209.png)
    
    하면 결과 안나옴
    
    원래는 [classname]_set을 통해서 역참조의 접근을 가능하게 해 줍니다. 해당 속성을 사용하여 코드를 수정해주면 다음과 같이 변하게 됩니다. 하지만 이걸 간단히 하기 위해 related_name = “” 으로 만들어줌. 
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2010.png)
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2011.png)
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2012.png)
    
    **refer - [https://hangjastar.tistory.com/201](https://hangjastar.tistory.com/201)**
    

## 5. django User model custom

---

- **방법1. User 모델과 1:1 관계의 테이블 추가하기**
    
    ```python
    from django.db import models
    from django.contrib.auth.models import User
    
    class Profile(models.Model):
    	user = models.OneToOneField(User, on_delete=models.CASCADE)
    	desc = models.TextField(max_length=255, blank=True)
    	location = models.CharField(max_length=30, blank=True)
    	birth = models.DateField(null=True, blank=True)
    ```
    

- **방법2. AbstractUser 모델 상속**
    
    ```python
    # users/models.py
    from django.db import models
    from django.contrib.auth.models import AbstractUser
    
    class User(**AbstractUser**):
    	birth = models.Date...
    ```
    
    ```python
    # settings.py
    
    ...
    
    AUTH_USER_MODEL = 'users.User'
    
    ...
    
    -> 이걸 settings.py 에 설정해줘야 함!
    ```
    
    오늘은 2번 방법으로!
    

방법 2번으로 설명해줌.

**DB 개론 - 데이터베이스 개론(3판) (석범이 형 ㅊㅊ)** 

## 6. Django DB 개론 (석범이형)

- 키의 특징
- 외래키, ERD 다루기
- SQL 다루기 -  [http://sqlfiddle.com/](http://sqlfiddle.com/)
- 실습 코드 노션 - [https://www.notion.so/DB-sql-c92f0c9bca9242d2afaccec755b08abe](https://www.notion.so/DB-sql-c92f0c9bca9242d2afaccec755b08abe)
    
    -SQL 직접 다루기
    

## 7. django 중급 세션 (피망마켓)

1. **static & media**
2. **대량 데이터 저장** → django-import-export 라이브러리 / 
    - bulk-create / [https://docs.djangoproject.com/en/1.8/ref/models/relations/](https://docs.djangoproject.com/en/1.8/ref/models/relations/)
3. **django ORM** (Post.objects.all() , get(), filter()) → 위 설명 참조
4. **django Foreignnkey** - 정참조, 역참조 → 위 설명 참조

## 8. django 로그인

- **인증과 인가**
    
    아마 **Reference - [https://velog.io/@dooyeonk/Django-인증-인가-구현하기](https://velog.io/@dooyeonk/Django-%EC%9D%B8%EC%A6%9D-%EC%9D%B8%EA%B0%80-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0)**  인 듯
    
    # 인증(Authorization) 인가(Authentication)
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2013.png)
    
    ## 인증
    
    - 유저의 아이디와 비밀번호를 확인하는 절차
    
    ⇒ 사용자가 입력한 정보를 가지고 이 사용자가 누구인지, 우리 서비스의 회원인지를 확인하는 것
    
    - 따라서 사전에 유저의 아이디와 비밀번호와 같은 정보들을 생성하고 저장할 수 있는 기능 필요
    
     
    
    가입을 한다면?
    
    ```java
    #my_project/user/views.py - UsersView(View):
        def post(self, request):
            data           = json.loads(request.body)
            valid_email_re = '^[a-z0-9]+[\._]?[a-z0-9]+[@]\w+[.]\w+$'
    
            try:
                new_email       = data['email']
                new_password    = data['password']
            except keyerror:
                return jsonresponse({'message': "key_error"}, status = 400)
    
            #email validation using re
            if not re.search(valid_email_re, new_email):
                return jsonresponse({'message': "invalid email"}, status = 400)
    
            #password validation
            if not len(new_password) >= 8:
                return jsonresponse({'message': "invalid password"}, status = 400)
    
            #duplacted value validation
            exist_user = user.objects.filter(email=new_email)
            if exist_user:
                return jsonresponse({'message': "name, phone or email is already exists"}, status = 400)
    
            hashed_password = bcrypt.hashpw(new_password.encode('utf-8'), bcrypt.gensalt()).decode('utf-8')
            user = user.objects.create(
                email         = new_email,
                password      = hashed_password
            )
    
            return jsonresponse({'message': "success"}, status = 200)
    ```
    
    → 비밀번호 암호화 한 것
    
    로그인을 한다면
    
    ```
    #my_project/user/views.py - LoginView(View):
        def post(self, request):
            data = json.loads(request.body)
    
            try:
                input_account  = data['account']
                input_password = data['password'].encode('utf-8')
            except Exception as error_msg:
                return JsonResponse({'message': 'KEY_ERROR'}, status = 400)
    
            try:
                user = User.objects.get(email=input_account)
            except Exception:
                return JsonResponse({'message': 'INVALID_USER'}, status = 400)
    
            if bcrypt.checkpw(input_password,user.password.encode('utf-8')):
                SECRET = SECRET_KEY
                access_token = jwt.encode({'id':user.id}, SECRET, algorithm=ALGORITHM)
    
                return JsonResponse({'message': 'SUCCESS',
                                     'access_token': access_token.decode('utf-8')}, status = 200)
    
            return JsonResponse({'message': 'INVALID PASSWORD OR ACCOUNT'}, status = 400)
    ```
    
    ## 인가
    
    - 유저가 요청하는 request를 실행할 수 있는 권한이 있는 유저인가 확인하는 절차
    - ex) 인스타의 경우 로그인하지 않았다면 게시물의 등록 삭제는 불가능하다
    
    - **데코레이터**
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2014.png)
    
    # 유저 비밀번호 암호화
    
    admin페이지로 가서 user를 확인해보자
    
    ## **사용자의 비밀번호를 그대로 저장하게 될 경우**
    
    - 만일 DB가 해킹 당할경우 비밀번호가 그대로 노출됨.
    - 사용자의 비밀번호가 암호화되지 않고 노출되어 저장된다면 서버의 내부인력,혹은 개발자가 악용할 수 있으므로 꼭 암호화 하여야함
    
    [](https://www.boannews.com/media/view.asp?idx=78058&page=1&kind=1)
    
    ## 단방향 해쉬함수
    
    - 원본 메시지를 변환하여 암호화된 메세지를 생성
    - 원본 메시지를 알면 암호화되기전 원본 메시지를 알 수 있지만 암호화된메시지로 원본 메시지를 구할 수 없어서 단방향성(one-way)
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2015.png)
    
    ### 다양한 해쉬함수들
    
    - sha
    - md
    - has
    - whirlpool
    
    ## 한계
    
    해시 함수를 이용하여 해싱 한 데이터를 DB에 저장하면 매우 안전할 것 같지만 현실은 그렇지 않다
    
    → 값이 변하지않는것이 문제
    
    ex) 123456@ㅇdsfkljshf을 암호화 하면 8d969eef6ecad3c29a3a629280e686cf0c3f5d5a86aff3ca12020c923adc6c92
    
    →
    
    [파이썬으로 문자열 SHA256로 암호화 하기](https://yeowool0217.tistory.com/536)
    
    [CrackStation - Online Password Hash Cracking - MD5, SHA1, Linux, Rainbow Tables, etc.](https://crackstation.net/)
    
    ## 단방향 해쉬함수의 취약점 및 보완
    
    - rainbow table attack
    
    [Understanding Rainbow Table Attack - GeeksforGeeks](https://www.geeksforgeeks.org/understanding-rainbow-table-attack/)
    
    ⇒ KEY STRETCHING 암호화(sha암호화한것을 sha를 한번더 하는것)를 한 비밀번호를 해킹하기위해 컴퓨팅하는시간을 오래걸리게해서 그이전에 비밀번호 변경으로 해킹당하는것을 최소화 
    
    ⇒ Salting - 해시된 암호에 무작위 값을 추가해 해시하는 방법
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2016.png)
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2017.png)
    
    ## Django가 패스워드를 생성하는 방법과 secret key
    
    secret keey
    
    - session
    - cookie
    - • PasswordResetView
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2018.png)
    
    ![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2019.png)
    
    `PASSWORD_HASHERS` 를 검색해보자
    
    ```python
    make_password를 검색해보자
    ```
    

---

---

---

이후로는 내가 점점 하면서 파보았던 것들

### csrf 보안토큰

---

**Reference** - [https://velog.io/@jupiter-j/CSRF토큰이란](https://velog.io/@jupiter-j/CSRF%ED%86%A0%ED%81%B0%EC%9D%B4%EB%9E%80)

- csrf 란 해커가 악성적으로 사용자의 비밀번호와 같은 것을 해킹하려 할 때 사용되는 방식 중 하나로, 클라이언트가 어떤 이유로 해커가 만든 서버에 reqeust를 보냈을 때, 그 request를 조작하여 원래 본 서버로부터 같은 쿠키의 같은 사용자라고 속여 데이터를 얻어 가는 방식이다.
- 항상 서버로부터 사용자가 request 했을 때 쉽게 받아가게 인증할 수 있는, OTP 비밀번호 같은 것이 토큰인데 위의 csrf방식을 방어하기 위해 사용자의 쿠키에 토큰을 심어두어 그 토큰을 검사함으로써 해커가 아닌 사용자임을 알 수 있게 하도록 하는 것이 즉, `@ csrf token` 이다.

### 어라 골뱅이네? → 데코레이터, 클로저 +`@ login_required` ( by 점프투 파이썬 )

---

**Reference** - [https://wikidocs.net/184210](https://wikidocs.net/184210) (점프투 파이썬)

→ 여기 설명 잘되어 있어서 사실상 여기보는 것이 나을 수도 있음.

- 데코레이터 함수는 본래 함수를 꾸미기 위해 만들어진 것으로,

수행시간을 재는 python 파일의 경우 다음과 같이 나타난다. 

```python
### 데코레이터 안 쓴 거

import time

def elapsed(original_func):   # 기존 함수를 인수로 받는다.
    def wrapper():
        start = time.time()
        result = original_func()    # 기존 함수를 수행한다.
        end = time.time()
        print("함수 수행시간: %f 초" % (end - start))  # 기존 함수의 수행시간을 출력한다.
        return result  # 기존 함수의 수행 결과를 리턴한다.
    return wrapper

def myfunc():
    print("함수가 실행됩니다.")

decorated_myfunc = elapsed(myfunc)
decorated_myfunc()
```

```python
### 데코레이터 쓴 거

import time

def elapsed(original_func):   # 기존 함수를 인수로 받는다.
    def wrapper():
        start = time.time()
        result = original_func()    # 기존 함수를 수행한다.
        end = time.time()
        print("함수 수행시간: %f 초" % (end - start))  # 기존 함수의 수행시간을 출력한다.
        return result  # 기존 함수의 수행 결과를 리턴한다.
    return wrapper

@elapsed
def myfunc():
    print("함수가 실행됩니다.")

myfunc()
```

이렇게 원래 함수 `elapsed()` 에다가 `myfunc()` 을 추가시킨 것과 같이

**데코레이터**란 

- 원래 함수 `elapsed()`에다가 `myfunc()` 같은 원하는 함수를 원래 함수 `elapsed()`인자로(파라미터로)  보내는 것 / 즉, 함수를 함수인자로 보내는 방법

예시로, 이와 비슷하게 위의  django인증 단계에서 쓰였던 `@login_required` 와 같이, 

만약 로그인한 사용자일 경우, `@login_required` 아래에 있는 원하는 함수를 인수로 보냄으로써 사용자가 로그인했을 때만 `login_required()`함수가 실행되며 아래의 함수도 함께 실행할 수 있도록 한다.

![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2020.png)

(사진 refer - [https://bio-info.tistory.com/172](https://bio-info.tistory.com/172))

## GET, POST 차이 ( 둘다 HTTP method임 )

---

보통 POST는 이미지나 데이터를 수정하는 경우에 보내는 http method 방식으로써, 그러한 정보가 숨겨져 전달되는 것과 달리 GET은 url에 원하는 주소나 가는 곳이 명확히 표현되어 있기 때문에 해킹하기 쉬운 경우가 많다. 

<aside>
😲 HTTP method 에는 GET,POST 이외에도 PUT, DELETE 가 있다.
→ 요즘 각광받고 있는 REST API 가 바로 이 HTTP method 와 관련이 있다??

</aside>

⇒ [https://velog.io/@yh20studio/CS-Http-Method-란-GET-POST-PUT-DELETE](https://velog.io/@yh20studio/CS-Http-Method-%EB%9E%80-GET-POST-PUT-DELETE) 

여기서 http method 방식 중 하나인 PUT ( 업데이트 ) 방식에 대해 설명하다가 밑에 링크를 통해 REST 까지도 설명을 하게 되면서 REST 또한 궁금하게 되었음.

## REST API 란?

- **REST 란? REST API란? RESTful API 란??**
    
    →[https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html) ( 잘 나타내져 있음 )
    

- 간단히 말해 **RE**presential **S**tate **T**ransport 로써, 상태 중심적인 통신 방법인데,

http 를 만들었던 주요 인물 중 하나가 HTTP ( **H**yper **T**ext **T**ransport **P**rotocal ) 즉, 하이퍼링크와 같은 비순차적인 hyper text를 통신하는 수단을 사용하는 방식이 아직 효율적이지 못하다고 생각해서 제시한 것이 REST 방식인 것이다.

자원을 나타내는 것을 큰 목표로, 자원은 URI 를 이용하고 상태는 HTTP method 방식을 이용함으로써 http 프로토콜의 방식을 그대로 이용하여 장점을 가지고 있다,-.

> 최근의 서버 프로그램은 다양한 **브라우저**와 안드로이폰, 아이폰과 같은 모바일 디바이스에서도 통신을 할 수 있어야 한다. 
( 즉, **모든 브라우저**가 사용하는 http 통신을 이용하는 REST 방식이 더욱 가치를 지님 )

이러한 멀티 플랫폼에 대한 지원을 위해 서비스 자원에 대한 아키텍처를 세우고 이용하는 방법을 모색한 결과, REST에 관심을 가지게 되었다.
> 

  

---

### 캐시와 쿠키의 차이점

---

![Untitled](%E1%84%91%E1%85%B5%E1%84%85%E1%85%A9%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%86%E1%85%B5%E1%86%BC%20%E1%84%87%E1%85%A2%E1%84%8B%E1%85%AE%E1%86%AB%20%E1%84%80%E1%85%A5%E1%86%BA%20%E1%84%87%E1%85%A9%E1%86%A8%E1%84%89%E1%85%B3%E1%86%B8%20d516b069aee74bb3810345f08b78d4b7/Untitled%2021.png)

(refer - [https://zorba91.tistory.com/163](https://zorba91.tistory.com/163))