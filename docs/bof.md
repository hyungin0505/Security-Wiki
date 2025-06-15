# Buffer Overflow
버퍼에 허용된 크기 이상의 데이터를 입력하여 임의의 메모리 공간을 침범할 수 있는 취약점이다.  
바이너리가 잘못된 메모리 주소에 접근하면 Segmentation Fault 오류를 발생시킨다.   

---

## Stack Buffer Overflow
불충분한 경계 검사로 인해 스택에서 버퍼 오버플로우가 발생할 경우 다양한 공격이 가능하다.  
스택에 인접하게 저장된 지역 변수의 값을 임의로 변경하거나 리턴 주소를 조작해 프로그램의 실행 흐름을 변경할 수도 있다.  

일반적으로 리턴 주소를 임의의 주소로 조작하여 제어 흐름을 탈취한다.

### 관련 공격 기법
- [Return-to-libc](./../return-to-library)
- [Retrun-Oriented-Programming](./../return-oriented-programming)

### 관련 방어 기법
- [Stack Canary](./../canary)
- [NX](./../nx)
- [ASLR](./../aslr)

---

## Heap Buffer Overflow
힙 영역에서 발생하는 버퍼 오버플로우를 말한다.  
동적으로 할당된 메모리 영역에서 메모리 청크의 메타데이터를 조작할 수 있다.  

또한, 함수 포인터를 임의로 덮어씌워 힙 구조를 변조할 수 있다.  
fastbin, tcache 등 힙의 관리 구조가 다양해 복잡한 구조에 대한 이해가 필요해서 스택 버퍼 오버플로우보다 난이도가 높은 편이다.  

### 관련 공격 기법
- Tcache Poisoning

### 관련 방어 기법