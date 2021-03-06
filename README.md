# EventLoopScheduler

A scheduler system that uses an event loop to schedule tasks,
to be ran in a non blocking system. It uses native functions and lambdas
to create tasks.

## Usage

Examples can be found in `examples` folder.

```c++
EventLoop scheduler;
// Turn on the LED every 2 secs
scheduler.repeat([] () {
  digitalWrite(13, HIGH);
  // Turn off the LED off after 1 sec
  scheduler.execute([] () {
    digitalWrite(13, LOW);
  }, 1, SECONDS);
}, 2, SECONDS);
```

Must be added to the loop function

```c++
scheduler.process();
```
