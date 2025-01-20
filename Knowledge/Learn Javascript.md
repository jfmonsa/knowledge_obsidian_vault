#index
+ High level
+ Single Threaded (Or multi threaded also: using workers in node and web workers in browser)
+ Garbage collected
+ interpreted and compiled (just-in-time JIT)
+ Prototype-based, multi-paradigm (OOP, imperative, declarative e.g functional 
+ Dynamic Language, Weak Typed
+ Non-blocking event loop
---
+ ==First-class Functions==, This means:
	+ Functions are treated like any other variable
	+ we can pass it as arguments, we can return them
+ Run time environments (Javascript engines): ==Browser and Node.js== )

# 1 - [[JS - Core Language]]
+ strict, vars, data types, casting, operators, comparisons, conditional branching, ??, loops, functions
# 2. [[JS - Objects]]
+ Objects: computed properties, methods; Object references and copying, memory management (reachability),  this and method shorthands, constructor operator (new), Optional chaining (?.), Symbol, object to primitive conversion (to number or strings)
# - [[JS - Asynchronous JavaScript]]
# Event Loop
+ El event loop es el que se encarga de implementar las operaciones asíncronas o el non-blocking. El event loop corre en el único hilo que existe en Node y como mencionamos anteriormente, al bloquear el único hilo de node, estamos bloqueando el event loop.
+ **Call Stack**: Cada vez que una función va a ser ejecutada pasa por el call stack.
+ **Callback Queue**: Aquí se agregan los callback o funciones que se ejecutan una vez las operaciones asíncronas hayan terminado

> El event loop es el que se encarga de revisar que el call stack este vacío para añadir lo que está dentro del callback queue y ejecutarlo.
# Browser
## Console
+ If we use `Shift + Enter`we can write multi-line code in the console

# Web Workers  / Wokers
## Concurrency vs Parallelism
+ Both refer to doing things at the same time

![[Pasted image 20241012101331.png]]
### Concurrency
+ JS can run code concurrently usign a single thread thanks to the ==event loop==
+ use only one cpu core

### Paralelism
+ Uses multiple cpu cores that otherwise will block the main thread
+ Ideal when you have multiple cpu-intensive work at the same time
+ not useful for I/O output operations (reading / writing from DB or disks) because it no depends on cpu
+ n available cores depends on ==actual physical cores of cpu==
