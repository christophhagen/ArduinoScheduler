# ArduinoScheduler

A very simple Scheduler for arduino platforms. Doesn't provide any advanced features, basically only executes given functions at a specified interval.

## Usage

Execute two tasks at certain intervals:

```C++
//forward declare functions
void execute1();
void execute2();

// The task objects
Task task1(execute1, 100, true); // Enabled
Task task2(execute2, 500, false); // Disabled

// This function will be called every 100 ms
void execute1() {
  // Do something
  
  // Wake up task 2
  task2.enable();
}

// This function will be called every 500 ms
void execute2() {
  // Do something else
}

void setup() {
  // Nothing to do here
}

void loop() {
  Task::runTasks();
}


```
