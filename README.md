Multithreading

CPU : The Central Processing Unit (CPU) is the brain of a computer, responsible for executing instructions from programs and performing calculations. It processes data, manages tasks, and controls hardware interactions. ex : AMD , Intel make cpu

CORES: A CPU core is an individual processing unit within a CPU that executes instructions independently. Modern processors have multiple cores, allowing them to handle multiple tasks simultaneously, improving speed and efficiency.

Types of CPU Cores: 

Single-Core CPU
  Only one core processes tasks at a time.
  Slower for multitasking.
  Used in older computers.

Dual-Core CPU
  Two cores work together, improving performance.
  Better multitasking than single-core CPUs.

Quad-Core CPU
  Four cores handle tasks in parallel.
  Common in desktops, laptops, and gaming systems.

Hexa-Core, Octa-Core, and More
  6-core (Hexa-core) and 8-core (Octa-core) CPUs are common in high-performance systems.
  Used for gaming, video editing, AI, and servers.
  Higher-core CPUs (16, 32, or more) are used in servers and workstations.

How CPU Cores Improve Performance
  More cores = better multitasking.
  Each core can run separate tasks (e.g., running multiple apps).
  Hyper-Threading (Intel) or Simultaneous Multithreading (SMT) allows one core to handle two threads, making it more efficient.

PREOGRAM : Set of instruction written in a programming language that tells computer how to perform a specific task , eg : MS Word is a program which helps usres to create and modify documents

PROCESS : A process is an instance of a program, that is going to be excuted. When a program runs , the OS creates a process to manage its execution , eg : when we open ms-word it becomes a  process in the OS 

THREAD : A thred is the smallest unit of execution within a process. A process can have multiple threads, which share the same resource but can run independently , eg : inside ms-word spell checker can be haldled by one thread 
        eg2: A webrowser like google chrome might use multiple thread for different tabs , with each tab runnning as a separate thread

MULTITASKING :  TBC 


How Java Handles Multithreading : 
In single core env , Java Multithreading is managed by jvm and the OS , which switch b/w threads to give the illusion of concurrency . The thread share the single code , and time slicing is used to manage thread execution.
In a multi-core env , Java Multithreading can take full advantage of the available cores. The JVM distribute threads across multiple cores, allowing true parallel execution of thread.

Java supports multithreading through its java.lang.Thread class and java.lang.Runnable interface.

Thread Creation : 

Steps For Thread creation while extending Thread class
1) A new class should be created that extends Thread.
2) The run method is overriden to define the code that constitues the new thread
3) start method is called to intitate the new thread

Main class : 

public class ThreadClass {
    public static void main(String[] args) {

        // connecting with other thread or running other thread
        World world = new World();
        world.start();

        for(int i = 0 ; i<10;i++){
            System.out.println(Thread.currentThread().getName());
        }
    }
}

Thread method overriden

public class World extends Thread{
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName());
        }
    }
}

Steps For Thread creation while implementing Runnable interface

1) A new class should be created that implements Runnable.
2) The run method is overriden to define the code that constitues the new thread
3) Thread object is created by passing an instance of MyRunnable
4) start method is called on the Thread object to intitate the new thread


public class RunnableInterfaceMain {
    public static void main(String[] args) {

        //Starting thread from runnable
        RunnableExample example = new RunnableExample();
        Thread t1 = new Thread(example);
        t1.start();

        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName());
        }
    }
}

public class RunnableExample implements Runnable{
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName());
        }
    }
}





