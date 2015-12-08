# Regex

Pattern match like a boss.



## Usage

Create:

```swift
let greeting = Regex("hello (world|universe)")

let magic: Regex = "(.*)"
```

Match:

```swift
if greeting.matches("hello universe!") {
  print("wow, you're friendly!")
}
```

_Pattern_ match:

```swift
switch someTextFromTheInternet {
case Regex("DROP DATABASE (.+)"):
  // TODO: patch security hole
default:
  break
}
```

Capture:

```swift
let greeting: Regex = "hello (world|universe|swift)"

if let subject = greeting.match("hello swift")?.captures[0] {
  print("ohai \(subject)")
}
```



## Installation

#### Swift Package Manager

Add a dependency to your `Package.swift`:

```swift
let package = Package(
  name: "MyPackage",
  dependencies: [
    // other dependencies...
    .Package(url: "https://github.com/sharplet/Regex.git", majorVersion: 0, minor: 2),
  ]
)
```

#### Carthage

Put this in your Cartfile:

```
github "sharplet/Regex"
```

#### CocoaPods

Put this in your Podfile:

```ruby
pod "STRegex"
```



## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).



## Development Setup

Development is currently only supported on Mac OS X. An Xcode project is
provided for your convenience.

Regex depends on Carthage for development:

```
$ brew install carthage
```

`xcpretty` is also recommended, for prettifying test output:

```
$ gem install xcpretty
```

After cloning the project, first set up your environment:

```
$ rake setup
```

Build and run the tests to ensure everything works:

```
$ rake
```



## License

See [LICENSE.txt](LICENSE.txt).
