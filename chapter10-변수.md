# 10장 변수 사용시 고려할 사항

## 10.2 변수 선언을 쉽게 만드는 방법

- 암시적 선언 기능을 사용하지 않는다.
- 모든 변수를 선언한다.
- 이름 규칙을 정한다. : 자주 사용되는 접미사에 대한 이름 규칙을 세워서 일관성 있게 하나만 사용한다.
- 변수의 이름을 검사한다. : 선언은 했지만 사용하지 않은 변수도 지적해준다.

## 10.3 변수 초기화 가이드라인

- 변수를 선언할 때 초기화 한다.
- 변수가 처음 사용되는 곳 근처에서 초기화한다.
- 이상적으로 각 변수가 처음 사용되는 곳 가까이에서 변수를 초기화하고 정의한다.
- 가능하다면 final이나 const를 사용한다.
- 카운터와 누산기를 주의한다. : 다음에 재사용하기 전에 초기화를 잊는 경우가 있다.
- 클래스의 맴버 데이터를 생성자에서 초기화한다.
- 다시 초기화해야 할 필요가 있는지 검사한다. : 변수를 다시 초기화해야 한다면 초기화 명령문을 반복되는 코드 안에 포함시킨다.
- 모든 변수를 자동으로 초기화하는 컴파일러 설정을 사용한다.
- 메모리 접근 도구를 사용해 부적절한 포인터를 검사한다. : 포인터가 유효하지 않은 메모리 영역을 참조하는지 검사한다.
- 프로그램을 시작할 때 메모리를 초기화 한다.

## 10.4 범위

### 변수에 대한 참조를 지역화 하라

변수 참조 사이에 있는 코드는 "취약한 구간"이다. 언제나 변수에 대한 참조를 가까운 곳에 함께 두어 지역화하는 것이 좋다.

### 변수의 "수명"을 가능한 한 짧게 유지한다.

변수의 수명은 변수가 참조되는 첫 번쨰 명령문에서 시작하고 변수가 참조되는 마지막 명령문에서 끝난다. 수명을 낮추면 취약 구간을 줄일 수 있다. 코드의 가독성이 높아진다.(한 번에 기억해야 하는 줄 수 가 적어져서) 초기화 오류가 발생할 가능성을 줄여준다. 큰 루틴을 작은 루틴으로 나눌 때 유용하다.

### 범위를 최소화하기 위한 일반적인 가이드라인

- 루프에서 사용되는 변수는 루프를 포함하고 있는 루틴의 시작이 아니라 루프 바로 앞에서 초기화 한다.
- 변수를 사용하기 바로 전까지 변수에 값을 할당하지 않는다.
- 연관된 명령문을 그룹화한다.
- 연관된 명령문 그룹을 별도의 루틴으로 나눈다.
- 처음에는 범위를 최대한 제한하고 필요한 경우에만 변수의 범위를 늘린다.

### 범위 최소화에 대한 조언

변수 범위의 최소화에 접근하는 방법은 개발자마다 가진 "편리함"과 "한 번에 이해 가능한 수준"에 대한 관점에 따라 다르다.

## 10.5 지속성

지속성의 가장 큰 문제는 변수가 실제보다 더 오랫동안 지속된다고 가정할 대 발생한다.

다음은 이런 문제를 피하기 위한 방법이다.

- 변수를 사용하고나면 그 변수를 "부적절한 값"으로 설정한다.
- 데이터가 지속적이지 않다고 가정하는 코드를 작성한다.
- 모든 데이터를 사용하기 바로 직전에 초기화하는 습관을 들인다.

## 10.6 결합 시점
결합 시점을 늦출수록 코드는 유연해진다. 결합 시점이 이를수록 유연성이 낮아지고 복잡성이 줄어든다.

## 10.7 데이터형과 제어 구조 사이의 관계

세가지 종류의 데이터와 그에 따른 제어 구조의 관계

- 순차적 데이터는 프로그램의 순차적 명령문으로 변환된다.
- 선택적 데이터는 프로그램에서 if와 case 명령문으로 변환된다.
- 반복되는 데이터는 프로그램에서 for, repeat, while 루프 구조로 변환한다.

## 10.8 변수를 한 가지 목적으로만 사용하기

- 각 변수를 한 가지 목적만을 위해서 사용하라.
- 선언된 모든 변수를 사용하는지 확인하라.

## 요점 정리

- 데이터 초기화는 오류가 발생하기 쉽기 때문에 예상치 못한 초기 값으로 인해서 발생하는 문제를 피하기 위하여 이 장에서 설명한 초기화 기법을 사용한다.
- 각 변수의 범위를 최소화한다. 변수에 대한 참조를 가까이 둔다. 루틴이나 클래스로 제한하고 전역 데이터는 사용하지 않는다.
- 같은 변수를 사용하는 명령문은 가능한 한 가까이 둔다.
- 초기에 결합하면 유연성이 떨어지지만 코드가 복잡해지는 것을 막을 수 있고, 늦게 결합하면 코드는 복잡해지지만 코드를 좀 더 유연하게 개발할 수 있다.
- 변수는 한 가지 목적으로 사용한다.

# 11장. 변수 이름의 기능

## 11.1 좋은 이름을 위한 고려 사항

### 이름을 지을 때 가장 중요한 고려 사항
변수 이름을 지을 때 그 이름이 변수가 나타내는 것을 완전하고 정확하게 설명하는지를 가장 중요하게 고려해야 한다. 좋은 이름을 생각해내는 효과적인 기법은 변수가 표현하는 것을 단어로 서술하는 것이다.

### 문제 지향
기억하기 쉬운 이름은 일반적으로 해결책보다 문제에 대해서 말한다. 좋은 이름은 "어떻게"보다 "무엇"을 표현하는 경향이 있다.

### 최적의 이름 길이

너무 짧은 이름은 충분한 의미를 전달하지 못한다. 변수 이름의 길이가 평균적으로 문자 10자에서 16자 사이일 때 프로그램을 디버깅하기 위해서 들이는 노력을 최소화할 수 있다는 사실을 발견했다.

### 범위가 변수명에 미치는 효과
긴 이름은 거의 사용하지 않는 변수나 전역 변수에 좋고 짧은 이름은 지역 변수나 반복문 변수에 좋다. 하지만 짧은 이름은 문제를 일으킬 수 있어 신중한 개발자들은 방어적으로 짧은 이름을 피한다.

### 변수 이름의 계산값 한정자

Total, Sum, Average, Max, Min, Record, String, Pointer와 같은 한벙자로 변수의 이름을 만들 경우 이름 끝에 한정자를 입력한다. 이러한 습관은 여러 가지 장점을 제공한다.

1. 변수 이름에서 사장 중요한 변수의 의미를 가장 잘 전달하는 부분이 앞부분이기 때문에 가장 눈에 띄고 잘 파악된다.
2. 이런 규약을 마련함으로써 `totalRevenue`, `revenueTotal`을 같은 프로그램에서 사용하는 혼란을 피할 수 있다.
3. 정돈된 느낌을 주고 일관성 있게 관리하여 이해하기 쉽고 유지보수도 쉽다.

Num은 관습적으로 앞에 위치한다. numCustomer, customerNum, numCustomers는 모두 다른 의미로 사용된다. Num을 사용하면 혼란을 일으키기 때문에 전체 고객의 수를 가리키기 위해 Count나 Total을 사용하고 특정 고객을 가리키는 데 Index를 사용함으로써 이러한 문제를 피하는 것이 가장 좋다.

### 일반적인 변수명의 반의어

반의어를 정확하게 사용하라. 일관성을 유지하고 가독성을 높이는 데 도움이 된다.

- begin/end
- first/last
- min/max
- locked/unlocked
- next/previous
- old/new
- opened/closed
- visible/invisible
- source/target
- source/destination
- up/down

## 11.2 특정 타입의 데이터 이름 짓기

### 반복문 인덱스 이름
변수를 반복문 외부에서 사용해야 한다면 반드시 i나 j보다는 더 의미있는 이름을 사용해야 한다.

### 상태 변수 이름
상태 변수에 대해서 flag보다 더 나은 이름을 생각해 본다.

### 불린 변수 이름
#### 전형적인 불린 변수의 이름을 기억한다.
- done
- error
- found
- success or ok

#### 참이나 거짓의 의미를 함축하는 불린 변수의 이름을 사용한다.
status를 error나 statusOK과 같은 이름으로 대체한다.

어떤 개발자들은 불린 변수 이름 앞에 Is를 입력하는 것을 좋아한다. 그렇게 하면 변수의 이름이 의문사가 된다. isDone? isError? 이 질문에 대한 참이나 거짓의 대답이 이 변수의 값을 제공한다. 이러한 접근 방법의 이점은 그것이 모호한 이름에는 어울리지 않다는 점이다. isStatus? 말이 안되는 이름이다. 단점은 간단한 논리 표현식에서 가독성이 떨어진다는 것이다. if (isFound) 는 if (found) 보다 가독성이 약간 떨어진다.

#### 긍정적인 불린 변수 이름을 사용한다.

notFound, notDone, notSuccessful 과 같은 부정적인 이름은 이 변수의 값이 부정이 되었을 때 읽기 어려워진다.

## 11.3 이름 규약의 효과
### 규악은 다음과 같이 여러 구체적인 이점을 제공한다.
- 더 많은 것을 당연하게 받아들인다. 상황에 따라 달라지는 결정이 아니라 한 가지로 일관된 결정을 하면 코드의 더 중요한 특성에 집중할 수 있다.
- 다른 프로젝트에서도 지식을 활용하는 데 도움을 준다.
- 새로운 프로젝트에서 좀 더 빠르게 코드를 배우게 해준다.
- 이름이 늘어나는 것을 줄여준다. : 이름 규약이 없으면 같은 것을 서로 다른 이름으로 부르기가 쉽다.
- 언어의 약점을 보완한다.
- 관련된 항목 사이의 관계를 강조한다. employeeAddress, employeePhone, employeeName

핵심은 어떤 규약이든 없는 것보다는 있는게 낫다는 것이다.

## 11.4 비형식적인 이름 규약
### 개발 언어에 독립적인 규약을 위한 가이드라인
- 변수의 이름과 루틴의 이름을 구별한다. : 변수와 객체의 이름은 소문자로 시작하고 루티으이 이름은 대문자로 시작한다.
- 클래스와 객체를 구별한다.
- 전역 변수를 식별한다.
- 멤버 변수를 식별한다.
- 타입 선언을 식별한다.
- 이름 상수를 식별한다.
- 열거형의 요소를 식별한다.

## 11.6 읽기 쉬운 짧은 이름
### 일반적인 축약어 가이드라인
- 표준 축약어를 사용한다.
- 불필요한 모음을 제거한다.
- 관사와 접속사를 제거한다.
- 각 단어의 첫 번째 문자나 처음 문자 몇 개를 사용한다.
- 첫 번째나 두 번째, 세 번째 문자에서 일관성있게 단어를 자른다.
- 각 단어의 첫 번째와 마지막 문자를 유지한다.
- 이름에서 가장 중요한 단어를 최대 세 단어까지 사용한다.
- 불필요한 접미사를 제거한다.
- 변수의 의미를 변경하지 않도록 한다.
- 각 변수 이름의 길이가 8자에서 20자 사이거나 사용하는 언어가 변수의 이름으로 제한한 문자 수가 될 떄가지 반복적으로 사용한다.

### 음성 축약
어떤 사람들은 단어의 철자보다는 소리에 기반을 두고 축약어를 생성하는 방법을 옹호하기도 한다.

#### 축약어에 대한 의견
다음은 함정을 피하기 위한 몇 가지 규칙이다.
- 단어에서 한 문자를 없애는 방법으로 축약하지 않는다. : 한 문자를 입력하는 것은 그다지 힘든 일이 아니며 한 문자를 절약한다고 해서 가독성이 떨어지는 것을 정당화하지는 못한다.
- 일관성 있게 축약한다. : 항상 같은 욱약어를 사용하라. 예를 들면 Num이나 No를 동시에 사용하지 말고 둘 중 하나만 사용하라.
- 발음할 수 있는 이름을 만든다. : XPstn 대신 xPos를 사용하고 ndsCmptg 대신 needsComp를 사용한다.
- 잘못된 발음을 유발할 수 있는 조합을 피한다. : B의 끝을 가리키기 위해서 BEND 대신 ENDB를 사용한다.
- 이름 충돌을 해결하기 위해서 유의어 사전을 사용한다. : 중복된 축약어를 쓰는 이름 충돌을 피하기 위해
- 매우 짧은 이름은 코드 내 변환 테이블을 사용하여 문서화한다.
- 모든 축약어를 프로젝트 수준의 "표준 축약어" 문서에 기록한다.
- 이름은 코드를 작성하는 사람보다 읽는 사람에게 더 중요하다는 점을 기억한다.

## 11.7 피해야 할 변수 이름
- 오해의 소지가 있는 이름이나 축약어를 피한다.
- 유사한 의미가 있는 이름을 피한다.
- 이름은 유사하지만 의미가 다른 변수를 피한다.
- 이름에 숫자를 넣는 것을 피한다.
- 이름에 철자가 틀린 단어가 없도록 한다.
- 영어에서 일반적으로 잘못 표기되는 단어를 피한다.
- 대소문자만으로 변수의 이름을 구분하지 않는다.
- 여러 가지 자연어를 사용하지 않는다.
- 표준 데이터형과 변수, 루틴의 이름은 사용하지 않는다.
- 변수가 표현하는 것과 전혀 관련이 없는 이름을 사용하지 않는다.
- 읽기 어려운 문자를 포함하는 이름은 피한다.

## 요점 정리
- 좋은 변수 이름은 프로그램의 가독성에 핵심적인 요소다. 반복문 인덱스와 상태 변수와 같은 특정한 종류의 변수는 특정한 사항을 고려해야 한다.
- 이름은 가능한 한 구체적이어야 한다. 모호하거나 하나 이상의 목적으로 사용될 수 있는 일반적인 이름은 보통 나쁜 이름이다.
- 이름 규약은 지역, 클래스, 전역 데이터를 구분한다. 그리고 형 이름, 이름 상수, 열거형, 변수를 구분한다.
- 개발 중인 프로젝트의 종류에 상관없이 변수 이름 규약을 적용해야 한다. 어떤 규약을 적용할지는 프로그램의 크기와 개발자의 수에 따라서 달라진다.
- 축약어는 최신 프로그램 언어에서는 거의 필요하지 않다. 정말로 축약어를 사용해야 한다면 프로젝트 사전에 축약어를 기록하거나 표준 접두사 접근 방법을 사용한다.
- 코드는 작성되는 것보다 훨씬 여러 번 읽힌다. 작성하기 편리한 것보다는 읽기 쉬운 이름을 선택한다.
