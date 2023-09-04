---
layout: post
title:  "[C#/TIL] 내일배움캠프 29일차 Unity 시작"
date:   2023-09-04 21:00:01 +0900
categories: jekyll update C#
---
## 들어가기에 앞서(어제 문제사항)
오늘은 어제에 이어 네이버 블로그가 아닌 다른 블로그를 시도해 보았다.
우선 캠프에서 추천한 깃허브 블로그로 진행해보고자 한다.

단점이라고 한다면 댓글, 검색 엔진 노출, 방문자 수 등등 원하는 기능이 있다면 일일히 구현해야하는 번거로움과 기능들을 익히는데에서 오는 어려움 등이 있겠다.

하지만 어렵기 때문에 결과물에 대한 평가도 높게 쳐주지 않을까 싶다.

## 오늘 배운 것(오늘 진행사항)

오늘은 유니티를 본격적으로 시작하여 프로젝트를 진행한다.

오늘 배운 내용을 간략히 정리하자면

1. 월드좌표와 로컬좌표

    월드좌표 : 상속되는 부모가 없는 오브젝트. "세상의 중심으로부터의 개체의 속성"

    로컬좌표 : 상속받는 부모로부터의 나의 위치. "부모의 값을 적용 받은 후 개체의 속성을 적용"


```C#
  public void OnLook(InputValue value)
    {
      Vector2 newAim = value.Get<Vector2>();
      Vector2 worldPos = _camera.ScreenToWorldPoint(newAim);
      newAim = (worldPos - (Vector2)transform.position).normalized;

      if (newAim.magnitude >= .9f)
        CallLookEvent(newAim);
    }
```

  위의 코드를 기반으로 하는 플레이어 개체에 대하여,

  해당 개체에서 마우스로의 벡터를 구하고 싶을 때

  마우스의 좌푯값 : UI좌표( : 스크린 좌표)로 화면의 좌상단을 기준으로 받아온다. 따라서 이것을 월드 좌표로 변환해 주어야한다.

  우리는 고등학교에서 AC벡터 - AB벡터 ==  BC벡터임을 배웠다.

  같은 원리로 ~~



2. GetAxis()와 GetAxisRaw()로 입력받기

3. Input System으로 입력받기

4. deltaTime이란

5. [SerializeField]란

6. SendMessage 방식( : 구독( : subscribe))

    옵저버 패턴 : 구독 + 호출

7. normalized



## 기억할 것

오늘 하루만에 배운 내용이 차고 넘쳐 모두 다 기억할 수 는 없으나,

 저 기능들 하나하나다 유용하고 기억할 만하기에 외우려 들기보다는 어느 프로젝트 어느 부분에 어떤 기능이 있었지 하고 인지만 하고 있자.

그리고 그 이후에 하나하나 조사하며 분석하고 기록해두도록 하자.

## 게임에 구현한다면?

pass

## 내일 할 일

1. Unity 강의 수강 완료.

2. 개인 프로젝트 시작.

3. Unity 강의에 나온 각 기능들 세밀하게 조사. 사용법 숙지.

4. 알고리즘 강의 수강 완료.


---
### Reference
[내일배움캠프][camp_link]


[camp_link]: https://spartacodingclub.kr/online/csharp