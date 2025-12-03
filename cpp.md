# 📘 C++ 객체지향 및 핵심 개념 요약 (A4 2장 분량)

## 1. 객체지향(OOP)의 4대 요소
- **추상화 (Abstraction)**: 복잡한 내부 로직 숨기고 핵심만 제공  
  ```cpp
  class Car { public: void drive(); };
  ```
- **캡슐화 (Encapsulation)**: 데이터 보호, 무결성 유지  
  ```cpp
  class Account { private: double balance; public: void deposit(double a); };
  ```
- **상속 (Inheritance)**: 기존 클래스 확장  
  ```cpp
  class Student : public Person {};
  ```
- **다형성 (Polymorphism)**: 같은 인터페이스, 다른 동작  
  ```cpp
  class Shape { virtual void draw(); };
  ```

---

## 2. 접근 권한 지정자
- **public**: 어디서나 접근 가능  
- **protected**: 클래스 + 자식 클래스  
- **private**: 클래스 내부  

👉 시험 포인트: 멤버 변수는 보통 `private`, 접근은 `getter/setter`.

---

## 3. 클래스와 객체
- 클래스 = 설계도  
- 객체 = 인스턴스  
```cpp
class Person { private: int age; public: void setAge(int a); };
Person p; p.setAge(20);
```

---

## 4. 생성자 & 소멸자
- **생성자**: 클래스명 동일, 반환형 없음, 자동 실행, 오버로딩 가능  
- **소멸자**: `~ClassName()`, 자동 실행, 오버로딩 불가  
```cpp
class A { A(); A(int x); ~A(); };
```

---

## 5. this 포인터
- 객체 자기 자신 가리킴  
- 멤버/매개변수 이름 구분  
```cpp
this->value = value;
```

---

## 6. const
- **const 함수**: 상태 변경 불가  
- **const 객체**: 읽기만 가능  

---

## 7. 동적 메모리
- `new/delete` → 메모리 관리  
- 배열은 `delete[]`  
👉 시험 포인트: 메모리 누수 방지  

---

## 8. 함수 오버로딩
- 같은 이름, 다른 매개변수  
- 컴파일 시 결정 (정적 바인딩)  
```cpp
void print(int); void print(double);
```

---

## 9. 함수 중첩
- 한 함수가 다른 멤버 함수 호출  
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
- **public 상속**: 부모 public → 자식 public  
- **protected 상속**: 부모 public → 자식 protected  
- **private 상속**: 부모 public → 자식 private  

---

## 12. 상속에서 생성자와 소멸자
- 실행 순서: 부모 생성자 → 자식 생성자 → 자식 소멸자 → 부모 소멸자  

---

## 13. 다중 상속
```cpp
class C : public A, public B {};
```
👉 시험 포인트: 다이아몬드 상속 문제 → `virtual` 상속으로 해결  

---

## 14. 바인딩
- **정적 바인딩**: 컴파일 시 결정 (오버로딩)  
- **동적 바인딩**: 실행 시 결정 (`virtual` 함수)  

---

## 15. 오버라이딩
- 상속 관계, 함수 이름/매개변수/반환형 동일  
- `virtual` 필요, `override` 권장  

---

## 16. static 멤버
- 클래스 당 1개만 존재  
- 객체 없이 호출 가능  
```cpp
static int count;
```

---

## 17. 가상 함수 & 추상 클래스
- **가상 함수**: 실행 시 결정  
- **순수 가상 함수**: `=0`, 반드시 자식 클래스에서 구현  

---

## 18. 템플릿
- **템플릿 함수**  
  ```cpp
  template<typename T> T add(T a, T b);
  ```
- **템플릿 클래스**  
  ```cpp
  template<class T> class Box { T data; };
  ```

---

## 19. STL
- **컨테이너**: vector, list, map, set…  
- **반복자**: 포인터처럼 순회  
- **알고리즘**: sort, find  

---

## 20. 콘솔 입출력
- **cin**: 입력  
- **cout**: 출력  
- **cerr**: 즉시 오류  
- **clog**: 버퍼링 오류  

---

## 21. ios 클래스
- 스트림 상태 확인  
  - good() 정상  
  - fail() 실패  
  - eof() 파일 끝  
  - bad() 심각 오류  

---

## 22. 입출력 조절자
- **setw(n)**: 출력 폭  
- **setfill(c)**: 채우기 문자  
- **setprecision(n)**: 소수점 자리수  
- **fixed**: 고정 소수점  
- **hex/dec/oct**: 진법 변환  

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

# 📑 전체 요약 (시험 대비)
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
