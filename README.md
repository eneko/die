# die

Terminating a Swift application with style:

```swift
func die<T>(_ message: @autoclosure () -> String, file: StaticString = #file, line: UInt = #line) -> T {
    preconditionFailure("💥 " + message(), file: file, line: line)
}
```

## Usage

Application or Playground:

```swift
let name: String? = nil
print(name!)
// Fatal error: Unexpectedly found nil while unwrapping an Optional value
```

```swift
let name: String? = nil
print(name ?? die("A girl has no name."))
Fatal error: 💥 A girl has no name: file MyPlayground.playground, line 5
```

Swift REPL:

```
1> let name: String? = nil
name: String? = nil
2> print(name!)
Fatal error: Unexpectedly found nil while unwrapping an Optional value
2018-03-02 22:16:27.761699-0800 repl_swift[65869:2477278] Fatal error: Unexpectedly found nil while unwrapping an Optional value
```

```
1> let name: String? = nil
name: String? = nil
2> print(name ?? die("A girl has no name."))
Fatal error: 💥 A girl has no name.: file repl.swift, line 6
2018-03-02 22:17:12.308533-0800 repl_swift[65869:2477278] Fatal error: A girl has no name.: file repl.swift, line 6
```

## Instalation
Copy the method above and paste it in your code. If you are not fond of the name `die()`, please rename it to something else. You can even use emoji:

```swift
print(name ?? 💣("A girl has no name"))
```
