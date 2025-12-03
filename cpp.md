# 📘 C++ 객체지향 및 문법 최종 합집합 정리 (20페이지 분량)

---

## 1. 객체지향(OOP)의 4대 요소
- **추상화 (Abstraction)**: 복잡한 내부 로직 숨기고 핵심 기능만 제공  
- **캡슐화 (Encapsulation)**: 데이터 보호, 무결성 유지, 접근 제어  
- **상속 (Inheritance)**: 기존 클래스 확장  
- **다형성 (Polymorphism)**: 같은 인터페이스, 다른 동작 수행  

```cpp
class Car { public: void drive(); };
class Account { private: double balance; public: void deposit(double a); };
class Student : public Person {};
class Shape { virtual void draw(); };
```

---

## 2. 접근 지정자 (Access Specifiers)
| 지정자 | 설명(KR) | 설명(EN) |
|--------|-----------|-----------|
| public | 어디서나 접근 가능 | Accessible from anywhere |
| protected | 클래스 내부 + 자식 클래스 | Accessible within class and subclasses |
| private | 클래스 내부에서만 | Accessible only within the class |

👉 **Tip:** 멤버 변수는 보통 `private`, 접근은 `getter/setter`.

---

## 3. 클래스와 객체
```cpp
class Person {
private: int age;
public:
    void setAge(int a) { age = a; }
    int getAge() { return age; }
};
Person p; p.setAge(20);
```
- 클래스 = 설계도  
- 객체 = 인스턴스  

---

## 4. 생성자 & 소멸자
- 생성자: 클래스명 동일, 반환형 없음, 자동 실행, 오버로딩 가능  
- 소멸자: `~ClassName()`, 자동 실행, 오버로딩 불가  

```cpp
class A {
public:
    A() { cout << "기본 생성자"; }
    A(int x) { cout << "매개변수 생성자"; }
    ~A() { cout << "소멸자"; }
};
```

---

## 5. this 포인터
- 객체 자기 자신 가리킴  
- 멤버/매개변수 이름 충돌 시 구분  

```cpp
void setValue(int value) { this->value = value; }
```

---

## 6. const 멤버 & const 객체
- const 함수: 상태 변경 불가  
- const 객체: 읽기만 가능  

```cpp
int get() const { return data; }
const A obj; obj.get(); // 가능
```

---

## 7. 동적 메모리
```cpp
int* p = new int(10); delete p;
int* arr = new int[5]; delete[] arr;
```
👉 delete 누락 → 메모리 누수 발생  

---

## 8. 함수 오버로딩
- 같은 이름, 다른 매개변수  
- 컴파일 시 결정 (정적 바인딩)  

```cpp
void print(int); void print(double);
```

---

## 9. 함수 중첩
```cpp
void A() { B(); }
```

---

## 10. 디폴트 매개변수
```cpp
int sum(int a, int b = 10);
sum(5); // sum(5,10)
```

---

## 11. 상속
- public 상속: 부모 public → 자식 public  
- protected 상속: 부모 public → 자식 protected  
- private 상속: 부모 public → 자식 private  

---

## 12. 상속에서 생성자와 소멸자
실행 순서: 부모 생성자 → 자식 생성자 → 자식 소멸자 → 부모 소멸자  

---

## 13. 다중 상속
```cpp
class C : public A, public B {};
```
👉 다이아몬드 문제 → virtual 상속  

---

## 14. 바인딩
- 정적 바인딩: 컴파일 시 결정 (오버로딩)  
- 동적 바인딩: 실행 시 결정 (`virtual` 함수)  

---

## 15. 오버라이딩
```cpp
class A { virtual void show(); };
class B : public A { void show() override; };
```

---

## 16. static 멤버
- 클래스 당 1개만 존재  
- 객체 없이 호출 가능  

```cpp
static int count;
int Class::count = 0;
```

---

## 17. 가상 함수 & 추상 클래스
```cpp
virtual void draw();
virtual void draw() = 0; // 추상 클래스
```

---

## 18. 템플릿
```cpp
template<typename T> T add(T a, T b);
template<class T> class Box { T data; };
```

---

## 19. STL
- 컨테이너: vector, list, map, set…  
- 반복자: 포인터처럼 순회  
- 알고리즘: sort, find  

---

## 20. 콘솔 입출력
- cin: 입력  
- cout: 출력  
- cerr: 즉시 오류  
- clog: 버퍼링 오류  

---

## 21. ios 클래스
- good() 정상  
- fail() 실패  
- eof() 파일 끝  
- bad() 심각 오류  

---

## 22. 입출력 조절자
- setw(n): 출력 폭  
- setfill(c): 채우기 문자  
- setprecision(n): 소수점 자리수  
- fixed: 고정 소수점  
- hex/dec/oct: 진법 변환  

---

## 23. 파일 입출력
```cpp
ifstream fin("a.txt");
ofstream fout("b.txt");
string s; getline(fin, s);
fout << s;
fin.close(); fout.close();
```

---

## 24. 전체 요약 (시험 대비)
- OOP: 추상화·캡슐화·상속·다형성  
- 접근권한: public/protected/private  
- 생성자/소멸자: 자동 실행  
- this/const: 자기 자신, 변경 불가  
- new/delete: 동적 메모리 관리  
- 오버로딩/오버라이딩: 정적 vs 동적  
- static/virtual: 클래스 공통, 실행 시 결정  
- 템플릿/STL: 타입 일반화, 자료구조·알고리즘  
- 입출력/파일 I/O: 스트림 기반 처리  

---

# 📑 시험 대비 1분 암기 버전
- **OOP**: 추상화·캡슐화·상속·다형성  
- **접근권한**: public/protected/private  
- **생성자/소멸자**: 자동 실행  
- **this/const**: 자기 자신, 변경 불가  
- **new/delete**: 동적 메모리 관리  
- **오버로딩/오버라이딩**: 정적 vs 동적  
- **static/virtual**: 클래스 공통, 실행 시 결정  
- **템플릿/STL**: 타입 일반화, 자료구조·알고리즘  
- **입출력/파일 I/O**: 스트림 기반 처리  

---
