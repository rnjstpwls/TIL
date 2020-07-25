### PJT01

> 보안상 문제풀이에 해당하는 내용은 Private (gitlab)에 저장하였으며 해당 파일은 풀이에 필요한 개념을 요점정리함

___



* Dictionary의 key에 해당하는 값을 return하는 방법

원하는 `dictionary`의 key값에 해당하는 value를 얻는 방법은 다음과 같다.

```python
dic = {'key1': value, 'key2': value2, ... }
dic['key1'] # value를 return한다.
```



* python 파일을 json파일로 변환하는 방법

```python
with open(file_name, 'w', encoding='UTF8') as make_file:
        json.dump(movie_info(movies_list, genres_list), make_file, ensure_ascii=False, indent=4)
```

설정에서 `ensure_ascii=False`를 꼭 써주어야 한다.  공식문서(doc)에서 json.dump를 검색하였다.

```markdown
json.dump(obj, fp, *, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False, **kw)¶
```

기본값인자로 `ensure_ascii=True`라고 되어있다. False로 바꿔줘야 한글이 정상적으로 나온다.



그리고 `indent=4`는 option인데 들여쓰기를 한다는 뜻이다. 4정도로 하면 이쁘게 json파일을 생성할 수 있다.

___

#### 후기



함수에서 input과 output이 어떤 자료형인지 항상 주의하자.

잘모르겠다면 print(type())을 찍어서 어떤 자료형이지 출력하면서 단계별로 진행하자.