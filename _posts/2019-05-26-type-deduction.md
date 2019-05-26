---
bg: "tools.jpg"
layout: post
title:  "Type Deduction"
crawlertitle: "About C++11 type deduction"
summary: "About C++11 type deduction"
date:   2019-05-26 20:09:47 +0700
categories: posts
tags: ['c++']
author: Miranda
---
c++98에서는 type deduction은 템플릿에 대한 것만 존재한다. c++11에 와서는 그 규칙을 조금 수정하고 auto와 decltype을 위한 규칙이 추가되었다.

### Template Type Deduction
{% highlight c++ %}
template<typename T>
void f(ParamType param);

f(expr);
{% endhighlight %}
컴파일 도중 컴파일러는 expr을 통해서 두가지 형식을 추론한다. T와 ParamType이다. 이 두가지 타입은 서로 다른 타입으로 추론되는 경우가 많다. ParamType은 const나 포인터 또는 레퍼런스가 붙는 경우가 흔하기 때문이다.

{% highlight c++ %}
template<typename T>
void f(const T& param);
int x = 0;
f(x);
{% endhighlight %}
위의 경우 T는 int형으로 추론되지만 ParamType은 const int&으로 추론된다. 이 예시에서는 T의 타입이 x의 타입과 같은 것으로 추론되지만, 실제로는 다르게 추론되는 경우도 있다. T에 대해 추론되는 형식은 x의 형태와 ParamType의 형태에 의존한다. 그 형태에 따라 세 가지 경우로 나뉜다.

1. ParamType이 포인터 또는 참조형식인 경우
    1. 만일 expr이 참조 형식이면 참조 부분을 무시한다.
    2. expr의 형식을 ParamType에 대해 패턴 부합 방식으로 대응시켜서 T의 형식을 결정
    {% highlight c++ %}
    template<typename T>
    void f(T& param)

    int x = 27;
    const int cx = x;
    const int& rx = x;

    f(x);    // T는 int, param은 int&
    f(cx);   // T는 const int, param은 const int&
    f(rx);   // T는 const int, param은 const int&
    {% endhighlight %}
    cx와 rx는 T의 형식에 const도 붙어서 추론되었다. 이는 const(상수) 키워드가 붙은 변수는 값이 변하지 않아야 하기 때문이다. ParamType에 &이 붙었기 때문에 상수를 지키기위해서는 const 키워드도 함께 추론해야하는 것이다.
    {% highlight c++ %}
    template<typename T>
    void f(const T& param)

    int x = 27;
    const int cx = x;
    const int& rx = x;

    f(x);    // T는 int, param은 const int&
    f(cx);   // T는 int, param은 const int&
    f(rx);   // T는 int, param은 const int&
    {% endhighlight %}
    하지만 위의 경우는 ParamType에 이미 const가 붙어서 추론되어있으므로 T형식 추론결과에는 const 키워드가 붙지 않는다.
    참조가 아닌 포인터인 경우도 위의 규칙을 따른다.


2. ParamType이 포인터도 아니고 참조도 아닌 경우
    ParamType이 포인터도 아니고 참조도 아닌 경우는 매개변수가 값으로 전달된다는 의미이다.
    1. expr의 형식이 참조이면 참조부분은 무시된다.
    2. expr이 const이면 const 역시 무시한다.
     {% highlight c++ %}
    template<typename T>
    void f(T param)

    int x = 27;
    const int cx = x;
    const int& rx = x;

    f(x);    // T는 int, param은 int
    f(cx);   // T는 int, param은 int
    f(rx);   // T는 int, param은 int
    {% endhighlight %}

3. ParamType이 보편 참조인 경우

### Auto
템플릿 형식 추론 방식을 기반으로 작동한다.

### decltype
