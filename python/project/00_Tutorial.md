### json 파일을 python 을 통해 읽는 방법

___

```python
import json

# json파일을 불러오는 코드
music_json = open('data/music.json', encoding='UTF8')

# json을 dict로 변환하는 코드
music_dict = json.load(music_json)
```

#### 1. json 외장함수를 import 한다.



#### 2. open(filename, mode)

``` markdown
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```

_file_

filename을 뜻한다. 

ex) `'data/musics.json'`

위치와 파일명을 사용해야 한다. 위치를 적지 않고 파일명만 쓸 경우 파이썬이 실행되는 위치에 파일명이 존재하는 경우 실행되지만 존재하지 않는 경우 Error가 발생한다.

> f-format 형식은 사용가능한가?
>
> 일단 가능한다. 하지만 f-format을 쓸 상황이 아니라면 다음과 같은 방법을 사용해보자.
>
> ```python
> filename = 'data/' + str(dic['name']) + '.json'
> open(filename, ... )
> ```



_mode_

| 문자  | 의미                                                         |
| :---- | :----------------------------------------------------------- |
| `'r'` | 읽기용으로 엽니다 (기본값)                                   |
| `'w'` | 쓰기용으로 엽니다, 파일을 먼저 자릅니다.                     |
| `'x'` | 독점적인 파일 만들기용으로 엽니다, 이미 존재하는 경우에는 실패합니다. |
| `'a'` | 쓰기용으로 엽니다, 파일이 존재하는 경우는 파일의 끝에 덧붙입니다 |
| `'b'` | 바이너리 모드                                                |
| `'t'` | 텍스트 모드 (기본값)                                         |
| `'+'` | 갱신(읽기 및 쓰기)용으로 디스크 파일을 엽니다                |

기본 모드는 `'r'` 입니다 (텍스트를 읽는 용으로 엽니다, `'rt'` 의 동의어). 

[출처 : docs.python.org]





*encoding*

파일을 디코딩하거나 인코딩하는 데 사용되는 인코딩의 이름이다.

사용하지 않을 경우 한글을 가져오지 못한다.(유니코드로 출력)

따라서 `encoding='UTF8'`을 꼭 써주도록 하자.



(나머지 option은 skip)



#### 3. json.load()

외장함수인 json에서 json파일을 python으로 바꿔준다.

python을 json파일로 바꿔주는건 json.dump()이다.



___

### 정리

json파일을 python으로 읽는다.

1. import json
2. open(filename, 'r')
3. json.load()



python파일을 json파일로 쓴다.

1. import json
2. oepn(filename, 'w')
3. json.dump()



___

#### 추가 .. 



#### _pprint란?_

```python
import pprint

pprint.pprint(music_info(musics_list))

```



pretty print 말 그대로 예쁜 데이터 인쇄기이다.

외장함수기때문에 사용하려면 import 해서 쓰도록 하자.

dictionary같은거 출력해서 보여줄때 들여쓰기를 예쁘게 해서 보여준다.