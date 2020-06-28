---
layout: post
title: 시간복잡도 (Time Complexity)
cover-img: /assets/img/path.jpg
use_math: true
gh-repo: daattali/beautiful-jekyll
---

시간복잡도는 알고리즘이 수행되는 데에 얼마나 많은 시간이 소요되는지 측정하는 하나의 개념이다.  
Time Complexity is a concept to tell how much time to solve a certain problem by an algorithm.  
시간복잡도를 표현하는 방식으로는 빅-오메가 (.Big Omega.), 빅 오(.Big O.), 빅 세타(.Big Theta.) 세 가지가 있으나, 업계에서는 사실상 빅 오만 사용하는 편이다.  
There are three ways to tell the time complexity - Big Omega, Big O, and Big Theta - but we usually use Big O notation.
Big O는 곧 알고리즘의 기본 연산의 횟수를 카운팅한 후, 최고차항의 계수를 없앤 값을 나타낸다. 모든 연산은 input이 무한하고, 또 input 값이 최악일 경우를 가정한다. (Worst Time Complexity, WTC)  
To tell an algorithm's time complexity, count all the basic operations in the algorithms, and surround the biggest term with O() eliminating the coefficient.

 * 알고리즘의 기본 연산
  * 복사 연산 Assignment Operation (A = 3, B = True)  
  * 산술 연산 Arithmetic Operation (3 + 5, A + 3)
  * 비교 연산 Comparison Operation (A < 4, B < 1)
  * 논리 연산 Logical Operation (and, or)
  * 비트논리 연산 Bitwise Logical Operation (birwise-and, bitwise-or)

_예시 1_

~~~ python
def plusone(n):
  target = n #복사연산 1번
  return target+1 #산술연산 1번
~~~

위의 경우는 주어진 수를 새로운 변수 (target)에 할당한 후 target에 1을 더한 값을 돌려주는 함수이다. 알고리즘의 수행 시간을 T(n)이라고 하면 T(n) = 2이다.  
그런데 여기서 최고차항은 상수항이므로 이를 빅 오로 표현하면 O(1)이다.
The example 1 is an algorithm to get one value, copy to a new variable and return it after increasing 1. To define the algorithm's performance time as T(n), T(n) = 2.  
However since the biggest term is the constant (2), we write its time complexity as O(1).  


~~~ python
def increment_on_list(list1):
  for i in range(len(list1)): #for문 >> n번 반복
    list1[i] = list1[i] + 1 # 산술연산 1번, 복사연산 1번 >> 연산 2번
  return list1
~~~

위의 경우는 주어진 배열(리스트)를 반복문을 이용하여, 각 원소마다 1씩 더한 후 해당 리스트를 돌려주는 함수이다.  알고리즘의 수행 시간을 T(n)이라고 하면 T(n) = 2n이나, 앞서 말했듯 Big O로 표기할 시에는 계수를 제거하므로 O(n)의 시간복잡도를 가진다고 할 수 있다.
The example 2 is an algorithm to get a list, increase 1 into every element in the list and return it. T(n) = 2n. And to write in Big O notation, its time complexity is O(n).

**주의사항**  
어떤 알고리즘의 수행시간이 T(n) = 3n + 4일 경우 이를 O(n)으로 표기하는 건 맞으나, T(n) = 3n + 4 = O(n)이라고 하는건 옳지 않다.  
When the time complexity is T(n) = 3n + 4, we can say it T(n) is O(n), but T(n) = O(n) is incorrect.  

![Expected Times](https://github.com/icehongsi/icehongsi.github.io/blob/master/assets/img/timecomplexity.png)

