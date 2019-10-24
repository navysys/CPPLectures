# 표준 템플릿 라이브러리 (STL: Standard Template Library)

소프트웨어 개발자가 프로그램을 작성할 때 프로그래밍 언어의 기본 기능만을 이용하지 않는다. 많은 소프트웨어 개발자들은 프로그램을 작성할 때 유용한 기능을
라이브러리로 만들고 이를 바탕으로 다음 작업을 진행한다. C++ 는 소프트웨어 개발자에게 유용한 함수들과 클래스를 표준 라이브러리로 제공한다. 
C++ 템플릿이 제너릭 프로그래밍의 기반인 것처럼 템플릿을 기반한 표준 라이브러리는 generic library(제너릭 라이브러리: 일반화된 라이브러리)로 어떤 데이터 자료형에 대해서도 적용 가능한 제너릭 알고리즘을 제공한다.
그러므로 STL은 템플릿으로 작성된 제너릭 클래스와 제너릭 함수 라이브러리를 제공하여 일반화 프로그래밍, 제너릭 프로그래밍이라는 새로운 프로그래밍 패러다임의 기반이 된다.
STL은 ISO/ANSI C++ 표준위원회에서 표준으로 채택되어 현재 C++ 표준 라이브러리에 포함되어 있다. STL을 사용하는 이유는 데이터 자료형에 종속된 함수 또는 자료구조가
아닌 자료형에 종속적이지 않은 일반적인 자료구조와 일반적인 알고리즘을 적용할 수 있기 때문이다

STL은 컨테이너(Container), 반복자(Iterator), 알고리즘(Algorithm)으로 구성된다. 
* 컨테이너(Container): 템플릿 클래스로 데이터를 저장하고 검색하기 위해 데이터를 저장하는 자료구조를 구현한 클래스로 vector, deque, list, queue, stack, set, map 이 있다. 모든 STL 컨테이너는 같은 타입의 데이터(객체 포함)의 모임이다.  
* 반복자(Iterator): 컨테이너에 저장된 데이타에 대한 포인터로 컨테이너에 저장된 원소들을 하나씩 순차적으로 순회 접근하기 위한 목적으로 정의된 것이다. STL의 반복자는 데이터를 읽을 때 사용하는 반복자, 데이터를 기록할 때 사용하는 반복자, 둘 다 가능한 반복자로 구분된다.  
* 알고리즘(algorithm): 알고리즘은 템플릿 함수로 컨테이너에 저장된 데이터에 대한 복사(copy), 검색(find, search), 삭제(remove), 정렬(sort), 대체(replace)
 등의 기능을 템플릿 함수로 구현한 것이다. 이들 함수는 컨테이너 클래스의 멥버 함수가 아니다. 
 
## STL 사용의 장점
* 전문가에 의해 만들어지고 테스트를 거친 검증된 라이브러리로 버그가 발생할 확률이 낮다.
* 객체 지향 기법과 일반화 프로그래밍 기법을 만들어져서 어떤 자료형에 대해서도 적용 가능하다.
* 대부분의 C++ 컴파일러를 지원하기 때문에 STL을 사용하면 개발 기간을 단축할 수 있고 버그가 없는 프로그램을 쉽게 만들 수 있음

## 컨테이너 분류
컨테이너는 컨테이너에 저장된 데이터의 구조에 따라 시퀀스 컨테이너(Sequence Container), 연관 컨테이너(Associative Container), 컨테이너 어뎁터(Container Adapter) 로 분류된다.
* 시퀀스 컨테이너는 데이터를 연속적인 메모리 공간에 순서대로 저장되어 있는 구조로 사용자가 데이터의 순서를 제어한다. 
시퀀스 이 컨테이너 구조에서는 자료의 추가가 빠르나 탐색할 때는 시간이 걸린다.   
** 예: vector, list, deque
* 연관 컨테이너는 데이터가 사전과 같이 일정 규칙에 따라 저장되어 있는 구조로 컨테이너가 데이터의 위치를 제어한다 데이터의 접근은 *key*를 통해서 이루어지며 자료들은 정렬되어 있다. 이 컨테이너 구조에서는 자료의 추가가 걸리지만 자료의 탐색은 매우 빠르다. 
** 예: map, set, multiset, mutimap
* 어뎁터 컨테이너는 시퀀스 컨테이너에 제약을 가해 데이터를 규정한 방법으로만 입출력되도록 컨테이너
** 예: stack, queue, priority queue

## 반복자(iterator)
반복자는 데이터가 순차적으로 저장된 컨테이너의 내부 데이터를 순회하면서 접근하는 방법을 제공
 
 ## 알고리즘의 분류
 STL 알고리즘은 시퀀스 알고리즘, 정렬 관련 알고리즘, 범용적인 수치 관련 알고리즘으로 분류되며 시퀀스 알고리즘은 변경 가능 시퀀스 알고리즘과 변경 불가능 시퀀스 알고리즘으로 분류된다. 
 
 ## 컨테이너 개념 
 STL의 모든 컨테이너는 공통적으로 다음과 같은 속성을 가진다.
 * 디폴트 생성자(default constructor)
 * 복사 생성자와 대입 (copy constructor and assignment: 깊은 복사(deep copy) 가 이루어짐
 * swap 함수  
 ** a.swap(b) 와 swap(a, b)가 제공되면 일정 시간이 이루어짐 
 * ==, !=: 콘텐츠 기반 비교 
 * lexicographic 순서 비교: 크기가 같지 않은 데어터 요소가 순서를 결정
 * begin(), end()
 * size(), empty(), max_size();
 
 ## 메모리 관리
 데이터는 힙(heap)의 연속된 메모리 공간에 저장된다. 
 
 * capacity(): 메모리 공간에 저장될 수 있는 데이터 요소의 개수
 * size(): 실제 저장된 데이터 요소 개수, 저장 공간의 나머지 영역은 사용하지 않고 있음
 * reserve(n): 실제 저장된 데이터 요소의 개수의 변경 없이 capacity를 n으로 증가시킴
 * 데이터의 삽입으로 필요한 경우 자동적으로 capacity를 증가시킴 
 
 capacity 증가가 더 큰 연속된 메모리 공간을 확보하는 경우 이미 저장된 데이터들이 새로 확보된 곳으로 모두 복사하여야 한다.
 insertion에 의한 capacity의 증가가 발생하는 경우 대략적인 평균적인 실행 시간을 constant로 하기 위해 capacity를 두 배로 증가한다. 
 Capacity는 감소하지 않는다. 메모리는 해지(release)하지 않는다. 
 