-----java------------
=====================

例子: class A{     private int i;      private A a = new A();  public A() {      }  public static void main(String[]args) {         A a = new A();      }  } 如上述代码,执行的时候会产生堆栈溢出.但是如果把A中的变量a换成static的变量则不会出现这个问题,java类库中java.lang.Boolean中就是这样做的!请问new A()时内存分配情况,还有a = new A(),他里面的成员变量是不是一直new下去啊?               对象的内存分配是在堆中完成的，而引用对象A的就是a是在栈中分配的内存，当你new A()时，会一直在栈中分配就是a,但每个变量a所指向的对象不相同，最终栈内存不够，报堆栈溢出 异常。将a属性声明为static，这就是所有类都将共享这个对象，并且只在首次new里在分配内存。
