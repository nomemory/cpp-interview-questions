* What is a reference ? 
* What is the difference between *pass-by-reference* and *pass-by-value* ?
* What are the main differences between a `struct` and a `class` ? 
* Are there any scenarios where you would normally use a `struct` over a `class` ?
* What are the main differences between a `reference` and a `pointer` ?
* What is *polymorphism* in C ?
* Explain the usage for the `virtual` keyword ?
* What is wrong with the following code:

```cpp
class A
{
    public:
        A() {}
        ~A(){}
};

class B: public A
{
    public:
        B():A(){}
        ~B(){}
};

int main(void)
{
  A* a = new B();
  delete a;
}
```

Answer: Undefined behavior because A destructor is not `virtual`.

* What is the output:

```cpp
unsigned char half_limit = 150;

for (unsigned char i = 0; i < 2 * half_limit; ++i)
{
    // do something;
}
```

Answer: Infinite Loop (overflow)

* Explain what the keyword `static` is doing ?
* What is the following:

```cpp
#include <iostream>
#include <string>
using namespace std;
 
void demo() {
    static int count = 0;
    cout << count << " ";
    count++;
}
 
int main()
{
    for (int i = 0; i < 5; i++)
        demo();
    return 0;
}
```

* What is the O(n) for the following code ?

```cpp
int main() {
  int n = 10; //n can be anything
  int sum = 0;
  float pie = 3.14;
  int var = 1;

  while (var < n){
    cout << pie << endl;
    for (int j=0; j<var; j++)
      sum+=1;
    var*=2;  
  }
  cout<<sum;
}
```

Answer is O(N)

* Write a C++ program that uses meta-programming to calculate the factorial of a given number at compile-time.

```cpp
#include <iostream>

template <int N>
struct Factorial {
    static const int value = N * Factorial<N - 1>::value;
};

template <>
struct Factorial<0> {
    static const int value = 1;
};

int main() {
    constexpr int num = 5; // Change this number to calculate factorial at compile-time
    std::cout << "Factorial of " << num << " is: " << Factorial<num>::value << std::endl;
    return 0;
}
```

# Code questions
