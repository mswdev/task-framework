# Task Framework

### Description
Task Framework for Java applications and programs. Although this includes methods for [TRiBot](http://www.tribot.org) scripts, it can easily be modified for almost anything. Easily implementable and works well with many types of projects. It's used to schedule and execute independent tasks in a controlled manner.

### How to create a task
1. Create a new class and implement the interface Task.
```java
public class ExampleTask implements Task {


    public boolean validate() {
        return false;
    }

    public void execute() {
    }

    public String toString() {
        return "";
    }

}
```

### How to create your main class
1. Create & Initialise a TaskManager object in your main class.
```java
public class Main {

    private static TaskManager task_manager = new TaskManager();

    public static void main(String[] args) {
    }

}
```
2. Using your TaskManager object you can call the addTasks() method initializing your tasks in the parameter.
```java
public class Main {

    private static TaskManager task_manager = new TaskManager();

    public static void main(String[] args) {
        addTasks();
    }

    private static void addTasks() {
        task_manager.addTask(new ExampleTask());
    }

}
```
3. Using your TaskManager object you can call the loop() method specifying your delay in the parameter. (NOTE: You may need to modify this method with Thread#sleep if you're not using this for TRiBot.)
```java
public class Main {

    private static TaskManager task_manager = new TaskManager();

    public static void main(String[] args) {
        addTasks();
        task_manager.loop(100, 150);
    }

    private static void addTasks() {
        task_manager.addTask(new ExampleTask());
    }

}
```

### Versions
**0.3 - 7/9/2016**
```sh
- Fixed a Bug with a sleep being in the wrong position causing high CPU issues.
```
**0.2 - 7/2/2016**
```sh
- Completely Re-written.
- Added the ability to set the status
- Added the ability to stop the script.
- Added documentation.
- Added ExampleVars.java
- Added ExampleMain.java
```
**0.1 - 5/2/2016**
```sh
- Release Version
```
