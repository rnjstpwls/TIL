* virtual environment

  1. `python -m venv venv`
  2. `source venv/Scripts/activate`
  3. `pip install django`
  4. `pip freeze > requirements.txt`

  

* django project 생성

  1. 프로젝트명 : **crud**

     `django-admin startproject crud .`

  2. 게시글 생성 앱 생성 : **articles**

     `python manage.py startapp articles`

  3. 앱 생성을 하였기 때문에 settings.py 가서 app 등록.

  4. `templates\base.html` 생성

  5. settings.py 에서 templates 경로 설정.

  6. url 분리



* CRUD articles

  1. models.py 에서 `Article` Model 생성하기 ( title, content, created_at, updated_at )

  2. forms.py 에서 `ArticleForm` ModelForm 생성하기

  3. migrate 하기

     `python manage.py makemigrations`

     `python manage.py migrate`

  4. index page 생성 (READ)

  5. create 구현 (CREATE)

  6. detail 구현 

  7. update 구현 (UPDATE)

  8. delete 구현 (DELETE)

  

* CRUD comment

  1. models.py 에서 `Comment` Model 생성하기
  2. forms.py 에서 `CommentForm` ModelForm 생성하기
  3. migrate 하기
  4. comment_create 생성
  5. comment_delete 생성



* auth

  1. `python manage.py startapp accounts`

     계정과 관련된 app 이름은 반드시 accounts로 한다.

  2. app 생성했으니 settings.py 에 등록.

  3. url 분리

  4. models.py ?

     => 만들필요없다. django에서 만든거 custom해서 사용하면 된다.

  5. urls.py -> views.py -> templates 순으로 signup 생성

     `from django.contrib.auth.forms import UserCreationForm`

  6. login도 만들필요 없다.

     `from django.contrib.auth import login as auth_login`

     함수 명을 login으로 해야되는데(그렇게 하도록 설정됨) import 함수명도 login이라 as 로 변경해준다.

     **주의** form 이름은 `AuthenticationForm` 이다.

     `from django.contrib.auth.forms import UserCreationForm, AuthenticationForm`

     **주의** AuthenticationForm 첫번째 인자는 request 이다.

     **주의** auth_login의 첫번째 인자도 request 이다. 두번째 인자는 .get_user() 이다.

     헷갈리니까 login 은 잘 기억하도록 하자.

     ```python
     def login(request):
         if request.method == "POST":
             form = AuthenticationForm(request, request.POST)
             if form.is_valid():
                 auth_login(request, form.get_user())
                 return redirect(request.GET.get('next') or 'articles:index')
         else:
             form = AuthenticationForm()
         context = {
             'form': form,
         }
         return render(request, 'accounts/login.html', context)
     ```

     

  7. logout 역시 login과 마찬가지로 import as 로 사용한다.

     **주의** auth_logout의 첫번째 인자는 request 이다.

     