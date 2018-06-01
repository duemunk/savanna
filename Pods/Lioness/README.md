<p align="center">
  <b> Lioness </b> &bull;
  <a href="https://github.com/louisdh/cub">Cub</a> &bull;
    <a href="https://github.com/louisdh/savannakit">SavannaKit</a>
</p>

<p align="center">
<img src="docs/resources/readme/logo.png" alt="Lioness Logo" style="max-height: 300px">
</p>

<h1 align="center">The Lioness Programming Language</h1>

<p align="center">
<a href="https://travis-ci.org/louisdh/lioness"><img src="https://travis-ci.org/louisdh/lioness.svg?branch=master" alt="Travis build status"/></a>
<a href="https://codecov.io/gh/louisdh/lioness"><img src="https://codecov.io/gh/louisdh/lioness/branch/master/graph/badge.svg" alt="Codecov"/></a>
<br>
<img src="https://img.shields.io/badge/version-0.5.2-blue.svg" style="max-height: 300px;" alt="version 0.5.2">
<a href="https://github.com/Carthage/Carthage"><img src="https://img.shields.io/badge/Carthage-compatible-4bc51d.svg?style=flat" style="max-height: 300px;" alt="Carthage Compatible"/></a>
<a href="https://developer.apple.com/swift/"><img src="https://img.shields.io/badge/Swift-4.0.2-orange.svg?style=flat" style="max-height: 300px;" alt="Swift"/></a>
<img src="https://img.shields.io/badge/Platforms-iOS%20%7C%20macOS%20%7C%20tvOS%20%7C%20watchOS%20%7C%20Linux-lightgrey.svg" style="max-height: 300px;" alt="Platform: iOS macOS tvOS watchOS">
<img src="https://img.shields.io/badge/extension-.lion-FF9C27.svg" style="max-height: 300px;" alt="Extension: .lion">
<br>
<a href="http://twitter.com/LouisDhauwe"><img src="https://img.shields.io/badge/Twitter-@LouisDhauwe-blue.svg?style=flat" style="max-height: 300px;" alt="Twitter"/></a>
<a href="https://paypal.me/louisdhauwe"><img src="https://img.shields.io/badge/Donate-PayPal-green.svg?style=flat" alt="Donate via PayPal"/></a>
</p>

Lioness is a high-level, dynamic, programming language designed for mathematical purposes. This project includes a lexer, parser, compiler and interpreter. All of these are 100% written in Swift without dependencies. 

The syntax of Lioness is inspired by Swift, and its feature set is akin to shader languages such as GLSL.

The standard library (abbreviated: stdlib) contains basic functions for number manipulation, including: max/min, ceil, floor, trigonometry, etc. However, more trivial functions, such as to calculate prime numbers, are not considered relevant for the standard library.


## Source examples
The following Lioness code calculates factorials recursively:

```swift
func factorial(x) returns {
	
    if x > 1 {
        return x * factorial(x - 1)
    }
	
    return 1
}

a = factorial(5) // a = 120
```

The following Lioness code uses a ```do times``` loop:

```swift
a = 1
n = 10
do n times {
    a += a
}
// a = 1024
```

*More examples can be found [here](Source%20examples).*

## Features

* Minimalistic, yet expressive, syntax
* No type system, language is dynamic
* 5 basic operators: ```+```, ```-```, ```/```, ```*``` and ```^```
	* ```^``` means "to the power of", e.g. ```2^10``` equals 1024
	* all operators have a shorthand, e.g. ```+=``` for ```+```
* Numbers
	* All numbers are floating point 
* Booleans
	* Can be evaluated from comparison
	* Can be defined by literal: ```true``` or ```false``` 
* Functions
	* Supports parameters, returning and recursion 
	* Can be declared inside other functions
* Structs
	* Can contain **any** type, including other structs  
* Loops
	* ```for```
	* ```while```
	* ```do times```
	* ```repeat while```
	* ```break```
	* ```continue```
* ```if``` / ```else``` / ```else if``` statements

## Running
Since the project does not rely on any dependencies, running it requires no setup. 

### macOS
Open ```Lioness.xcworkspace``` (preferably in the latest non-beta version of Xcode) and run the ```macOS Example``` target. The example will run the code in ```A.lion```. The output will be printed to the console.

## Installing framework
 
### Using Swift Package Manager

Add to your `Package.swift` file's `dependencies` section:

```swift
.Package(url: "https://github.com/louisdh/lioness.git",
		         majorVersion: 0, minor: 5)
```

### Using [CocoaPods](http://cocoapods.org)

Add the following line to your ```Podfile```:

```ruby
pod 'Lioness', '~> 0.5'
```

### Using [Carthage](https://github.com/Carthage/Carthage)
Add the following line to your ```Cartfile```:

```ruby
github "louisdh/lioness" ~> 0.5
```
Run ```carthage update``` to build the framework and drag the built ```Lioness.framework``` into your Xcode project.


## Standard Library
*Please note: Lioness is currently in beta*

The Standard Library is currently under active development. There currently is no one document with everything from the stdlib. The best place to look for what's available is in [the source files](Sources/Lioness/Standard%20Library/Sources/).

## Roadmap
- [x] Structs
- [ ] Completion suggestions (given an incomplete source string and insertion point)
- [ ] Breakpoint support in interpreter
- [ ] Stdlib documentation (Dash?)
- [ ] Compiler warnings
- [ ] Compiler optimizations
- [x] Faster Lexer (without regex)
- [x] Support emoticons for identifier names
- [ ] ```guard``` statement
- [ ] A lot more unit tests
- [x] Linux support

## Xcode file template
Lioness source files can easily be created with Xcode, see [XcodeTemplate.md](XcodeTemplate.md) for instructions.


## Architecture
A detailed explanation of the project's architecture can be found [here](docs/Architecture.md).

## License

This project is available under the MIT license. See the LICENSE file for more info.
