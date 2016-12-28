# Swift-Style
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [**Swift-Style-Guide**](#swift-style-guide)
  - [命名](#%E5%91%BD%E5%90%8D)
    - [大小写](#%E5%A4%A7%E5%B0%8F%E5%86%99)
    - [缩写](#%E7%BC%A9%E5%86%99)
    - [协议](#%E5%8D%8F%E8%AE%AE)
    - [枚举](#%E6%9E%9A%E4%B8%BE)
    - [类前缀](#%E7%B1%BB%E5%89%8D%E7%BC%80)
    - [方法选择器](#%E6%96%B9%E6%B3%95%E9%80%89%E6%8B%A9%E5%99%A8)
    - [泛型](#%E6%B3%9B%E5%9E%8B)
  - [代码结构](#%E4%BB%A3%E7%A0%81%E7%BB%93%E6%9E%84)
    - [协议遵守](#%E5%8D%8F%E8%AE%AE%E9%81%B5%E5%AE%88)
    - [无用代码](#%E6%97%A0%E7%94%A8%E4%BB%A3%E7%A0%81)
    - [最小量的导入](#%E6%9C%80%E5%B0%8F%E9%87%8F%E7%9A%84%E5%AF%BC%E5%85%A5)
  - [类和结构体](#%E7%B1%BB%E5%92%8C%E7%BB%93%E6%9E%84%E4%BD%93)
    - [类和结构体的选择](#%E7%B1%BB%E5%92%8C%E7%BB%93%E6%9E%84%E4%BD%93%E7%9A%84%E9%80%89%E6%8B%A9)
    - [struct 的优点](#struct-%E7%9A%84%E4%BC%98%E7%82%B9)
    - [self 关键字的使用](#self-%E5%85%B3%E9%94%AE%E5%AD%97%E7%9A%84%E4%BD%BF%E7%94%A8)
    - [计算属性](#%E8%AE%A1%E7%AE%97%E5%B1%9E%E6%80%A7)
    - [属性观察](#%E5%B1%9E%E6%80%A7%E8%A7%82%E5%AF%9F)
    - [懒加载属性](#%E6%87%92%E5%8A%A0%E8%BD%BD%E5%B1%9E%E6%80%A7)
    - [final 关键字](#final-%E5%85%B3%E9%94%AE%E5%AD%97)
  - [函数声明](#%E5%87%BD%E6%95%B0%E5%A3%B0%E6%98%8E)
  - [闭包表达式](#%E9%97%AD%E5%8C%85%E8%A1%A8%E8%BE%BE%E5%BC%8F)
  - [类型](#%E7%B1%BB%E5%9E%8B)
    - [常量](#%E5%B8%B8%E9%87%8F)
    - [可选类型](#%E5%8F%AF%E9%80%89%E7%B1%BB%E5%9E%8B)
    - [类型推断](#%E7%B1%BB%E5%9E%8B%E6%8E%A8%E6%96%AD)
  - [访问控制](#%E8%AE%BF%E9%97%AE%E6%8E%A7%E5%88%B6)
  - [控制流](#%E6%8E%A7%E5%88%B6%E6%B5%81)
    - [集合操作](#%E9%9B%86%E5%90%88%E6%93%8D%E4%BD%9C)
  - [风格](#%E9%A3%8E%E6%A0%BC)
    - [正确性](#%E6%AD%A3%E7%A1%AE%E6%80%A7)
    - [属性命名](#%E5%B1%9E%E6%80%A7%E5%91%BD%E5%90%8D)
    - [结构体构造器](#%E7%BB%93%E6%9E%84%E4%BD%93%E6%9E%84%E9%80%A0%E5%99%A8)
    - [空格](#%E7%A9%BA%E6%A0%BC)
    - [分号](#%E5%88%86%E5%8F%B7)
    - [圆括号](#%E5%9C%86%E6%8B%AC%E5%8F%B7)
    - [语法糖](#%E8%AF%AD%E6%B3%95%E7%B3%96)
    - [隐式成员表达式](#%E9%9A%90%E5%BC%8F%E6%88%90%E5%91%98%E8%A1%A8%E8%BE%BE%E5%BC%8F)
    - [Golden Path](#golden-path)
  - [注释](#%E6%B3%A8%E9%87%8A)
- [**API Design Guidelines**](#api-design-guidelines)
  - [API 命名](#api-%E5%91%BD%E5%90%8D)
    - [提倡清晰的用法](#%E6%8F%90%E5%80%A1%E6%B8%85%E6%99%B0%E7%9A%84%E7%94%A8%E6%B3%95)
    - [[尽量]()流利的使用](#%E5%B0%BD%E9%87%8F%E6%B5%81%E5%88%A9%E7%9A%84%E4%BD%BF%E7%94%A8)
  - [约定](#%E7%BA%A6%E5%AE%9A)
    - [一般约定](#%E4%B8%80%E8%88%AC%E7%BA%A6%E5%AE%9A)
    - [参数](#%E5%8F%82%E6%95%B0)
    - [参数标签（参数外部名）](#%E5%8F%82%E6%95%B0%E6%A0%87%E7%AD%BE%EF%BC%88%E5%8F%82%E6%95%B0%E5%A4%96%E9%83%A8%E5%90%8D%EF%BC%89)
- [**目录命名和文件结构**](#%E7%9B%AE%E5%BD%95%E5%91%BD%E5%90%8D%E5%92%8C%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84)
  - [目录命名](#%E7%9B%AE%E5%BD%95%E5%91%BD%E5%90%8D)
  - [文件结构](#%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84)
    - [类型外部结构](#%E7%B1%BB%E5%9E%8B%E5%A4%96%E9%83%A8%E7%BB%93%E6%9E%84)
    - [类型内部结构](#%E7%B1%BB%E5%9E%8B%E5%86%85%E9%83%A8%E7%BB%93%E6%9E%84)
    - [私有嵌套类型](#%E7%A7%81%E6%9C%89%E5%B5%8C%E5%A5%97%E7%B1%BB%E5%9E%8B)
- [**参考**](#%E5%8F%82%E8%80%83)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## **Swift-Style-Guide**

### 命名

#### 大小写

类型 (类，结构体，枚举和协议) 命名应该是 UpperCamelCase 的形式，其他所有的命名全部是 lowerCamelCase 的形式。

```swift
private let maximumWidgetCount = 100

class WidgetContainer {
    var widgetButton: UIButton
    let widgetHeightPercentage = 0.85
}
```

#### 缩写

避免使用缩写和首字母略缩词，缩写词出现的时候尽量全部大写，不过如果缩写被用于命名的起始，那么就全部小写。

```swift
let urlString: URLString
let userID: UserID
```

#### 协议

描述是什么的协议读起来应该是个名词：`Collection`,  `WidgetFactory`，描述能力的协议应该用 able、ible、 ing 作为后缀：`Equatable`,  `Resizing`。如果前两种方法都不能明确表达，可以给它加上 `protocol` 后缀。

#### 枚举

Swift 3 中枚举值规定用小写开头。

```swift
enum Shape {
    case rectangle
    case square
    case rightTriangle
    case equilateralTriangle
}
```
#### 类前缀

Swift 类型自动被模块名设置了名称空间，所以不需要加前缀。如果两个来自不同模块（即 target）的命名冲突了，可以附加一个模块名到类型命名的前面来消除冲突。

```swift
import SomeModule
let myClass = MyModule.UsefulClass()
```

注：[命名空间](http://swifter.tips/namespace/)

#### 方法选择器

在可推测上下文的环境中，使用类型推断而不要用全名称选择器。

**Preferred:**

```swift
let sel = #selector(viewDidLoad)
```

**Not Preferred:**
```swift
let sel = #selector(ViewController.viewDidLoad)
```
#### 泛型

泛型参数应该是 uppercamelcase 形式，尽量使参数名描述它的作用，如果参数名并没有有意义的关系或角色，那么就用单个大写字母表示：`T`, `U`,或 `V`。

```swift
struct Stack<Element> { ... }
func writeTo<Target: OutputStream>(inout target: Target)
func max<T: Comparable>(x: T, _ y: T) -> T
```

### 代码结构

将相同功能逻辑的代码块放到单独的扩展当中，每个扩展都应该用 `// MARK: -` 分割开。`// MARK: -` 中的每个空格都是必要的。在每个 `// MARK: -` 可用 `// MARK:` 再来细分业务。

#### 协议遵守

当我们对一个类添加协议时，推荐使用一个单独的类扩展来实现协议的方法。这可以保持协议相关的方法聚合在一起，同时也可以简单的标识出一个协议对应类中需要实现哪些对应的方法。

```swift
class MyViewcontroller: UIViewController { }

// MARK: - UITableViewDataSource
extension MyViewcontroller: UITableViewDataSource { }

// MARK: - UIScrollViewDelegate
extension MyViewcontroller: UIScrollViewDelegate { }
```

因为编译器不允许派生类重复遵守父类的协议，所以不是必须复制父类的扩展组到派生类结构中，特别是当派生类是个终点类并且只有少数方法需要被重写的时候。如果父类本身自带多个协议，如：`UITableViewController`，也没必要单独创建两个扩展做数据源和代理。关于这条规则的 issue: [Protocol conformance](https://github.com/raywenderlich/swift-style-guide/issues/116)。

注：[Overriding declarations from extensions](https://github.com/ksm/SwiftInFlux/blob/master/README.md#overriding-declarations-from-extensions) 。由于当前 Swift 只能在扩展里重写兼容 Objective-C 的方法和属性，那么只有添加 `@objc` 标记或者基类是 `NSObject` 的类中的方法才能在扩展当中被重写。

```swift
protocol Flyable {
    func fly()
}

class Bird: Flyable {
    @objc func fly() {  }
}

class Swift: Bird {  }

extension Swift {
    override func fly() {  }
}
```

#### 最小量的导入

保持最小量的导入，比如当导入 `Foundation` 能够满足需求的时候就不要导入 `UIKit`。

### 类和结构体

#### 类和结构体的选择

结构体实例总是通过值传递，类实例总是通过引用传递。

使用 struct 来代替 class 作为数据模型有很多好处。值类型是非常有优势的：

- 安全性：因为 struct 是用值类型传递的，它们没有引用计数。

- 内存：由于他们没有引用数，他们不会因为循环引用导致内存泄漏。

- 速度：值类型通常来说是以栈的形式分配的，而不是用堆。因此他们比 class 要快很多。

- 拷贝：在 Objective-C 里拷贝一个对象必须选用正确的拷贝类型（深拷贝、浅拷贝）。 Swift 中值类型的拷贝则非常轻松。

- 线程安全：值类型是自动线程安全的。无论你从哪个线程去访问你的 struct ，都非常简单。

但是现有项目中使用 RxSwift， viewModel 中的各种 map、filter 方法都是 `@escape` 闭包，在 Swift 3 中限制逃逸闭包不可以隐式捕获 `inout` 参数， 所以 struct 的 mutating 方法中不能使用逃逸闭包。

注：[Limiting inout capture to @noescape contexts](https://github.com/apple/swift-evolution/blob/master/proposals/0035-limit-inout-capture.md)

如下一段 RxSwift 代码， filter 是一个逃逸闭包，`changedCellModels` 是一个数组，如果此时类型是 struct 则会报错：**Closure cannot implicitly capture a mutating self parameter**。所以这种需要修改自身属性的 viewModel 采用 class 类型。

```swift
fileprivate mutating func updateTreatment() -> Observable<Bool> {
    return  submitButtonDidTap
        .filter{ _ in
            self.changedCellModels = self.cellModels
                .filter { return $0.hasChanged.value == true }
            if self.changedCellModels.isEmpty {
                self.updateInvalid.onNext(Void())
            }
            return !self.changedCellModels.isEmpty
        }
        // etc
        ..........
}
```

一般来说 viewController 的 viewModel 常出现这种情况，view（如各种 cell） 的 viewModel则很少出现，所以在项目中前一类使用 class 类型，后一类采用 struct 类型（遇到前述需要修改自身值的情况可换做 class）。

#### self 关键字的使用

为了保持简洁，避免使用 `self` 关键词，Swift 不需要使用 `self` 来访问对象属性和调用对象方法。

必须使用 `self` 来区分构造器中属性命名和参数命名，还有在闭包表达式中引用属性值(编译器需要区分):

```swift
class BoardLocation {
    let row: Int, column: Int
    init(row: Int, column: Int) {
        self.row = row
        self.column = column
        let closure = {
            print(self.row)
        }
    }
}
```
#### 计算属性

为了保持简洁，如果一个计算属性是只读的，请忽略掉 `get` 语句。只有在需要定义 `set` 语句的时候，才提供 `get` 语句。

```swift
var diameter: Double {
    return radius * 2
}
```

#### 属性观察

尽管可以在 `willSet`、`didSet` 以及 `set` 方法中使用自定义的名称，但还是用默认的 `newValue`、`oldValue`变量名统一风格。

#### 懒加载属性

使用懒加载对对象进行更细粒度的生命周期控制，特别是当 `UIViewController` 懒加载视图的时候，我们可以使用一个会被立即调用的闭包 `{ }()` 或者调用私有的工厂方法：

```swift
lazy var locationManager: CLLocationManager = self.makeLocationManager()
private func makeLocationManager() -> CLLocationManager {
    let manager = CLLocationManager()
    manager.desiredAccuracy = kCLLocationAccuracyBest
    manager.delegate = self
    manager.requestAlwaysAuthorization()
    return manager
}
```

注：

- 这里没有造成循环引用，所以不需要使用 `[unowned self]`。
- Location manager 有个弹出界面请求权限的附带作用，细粒度的生命周期控制就有了意义。

#### final 关键字

当类不再被继承时将类标记为 `final`。

### 函数声明

API 详细规范见下 **API Design Guidelines**。

保证短的函数定义在同一行中，并且包含左大括号：

```swift
func reticulateSplines(spline: [Double]) -> Bool {
    // reticulate code goes here
}
```

在一个长的函数定义时，在适当的地方进行换行：

```swift
func reticulateSplines(spline: [Double], adjustmentFactor: Double,
                       translateConstant: Int, comment: String) -> Bool {
    // reticulate code goes here
}
```

如果你的函数需要返回多个参数，那么尽可能地使用 `Tuple` 来代替 `inout` 参数。如果你会多次使用某个元组，那么应该使用 `typealias` 设置别名。如果返回的参数超过三个，那么应该使用结构体或者类来替代。

```swift
func pirateName() -> (firstName: String, lastName: String) {
    return ("Guybrush", "Threepwood")
}
let name = pirateName()
let firstName = name.firstName
let lastName = name.lastName
```

**多参数过长时的调用：**

在调用参数过长的多参数函数的时候，把多个参数放置到单独的行中，左对齐。

```swift
let alert = UIAlertController(
    title: NSLocalizedString("Oops! Firefox crashed", comment: "Title for prompt displayed to user after the app crashes"),
    message: NSLocalizedString("Send a crash report so Mozilla can fix the problem?", comment: "Message displayed in the crash dialog above the buttons used to select when sending reports"),
    preferredStyle: UIAlertControllerStyle.Alert
)
```

对于大型的数组或者字典类型，应该将其分割到多行内，`[` 与 `]` 类比于花括号进行处理。对于闭包而言也应该同样适合于该规则（如果第一个参数无参数标签，则不单独放在一行）。

```swift
someFunctionWithABunchOfArguments(noLableArgument,
    someArrayArgument: [
        "dadada daaaa daaaa dadada daaaa daaaa dadada daaaa daaaa",
        "string one is crazy - what is it thinking?"
    ],
    someDictionaryArgument: [
        "dictionary key 1": "some value 1, but also some more text here",
        "dictionary key 2": "some value 2"
    ],
    someClosure: { parameter1 in
        print(parameter1)
    }
)
```

尽可能地使用本地变量的方式来避免多行的判断语句。

```swift
let firstCondition = x == firstReallyReallyLongPredicateFunction()
let secondCondition = y == secondReallyReallyLongPredicateFunction()
let thirdCondition = z == thirdReallyReallyLongPredicateFunction()
if firstCondition && secondCondition && thirdCondition {
    // do something
}
```

**自定义代理方法的第一个参数应该是被代理方，且不包含外部名。**

**Preferred:**

```swift
func namePickerView(_ namePickerView: NamePickerView, didSelectName name: String)
func namePickerViewShouldReload(_ namePickerView: NamePickerView) -> Bool
```

**Not Preferred:**

```swift
func didSelectName(namePicker: NamePickerViewController, name: String)
func namePickerShouldReload() -> Bool
```

### 闭包表达式

尽可能地使用尾随闭包表达式，除非需要显示地声明闭包参数的外部参数名。

**Preferred:**

```swift
UIView.animateWithDuration(1.0) {
    self.myView.alpha = 0
}

UIView.animateWithDuration(1.0,
    animations: {
        self.myView.alpha = 0
    },
    completion: { finished in
        self.myView.removeFromSuperview()
    }
)
```

**Not Preferred:**

```swift
UIView.animateWithDuration(1.0, animations: {
    self.myView.alpha = 0
})

UIView.animateWithDuration(1.0,
    animations: {
        self.myView.alpha = 0
    }) { f in
        self.myView.removeFromSuperview()
}
```

当单个闭包表达式上下文清晰时，使用隐式的返回值：

```swift
attendeeList.sort { a, b in
    a > b
}
```

尾随闭包链式调用时应该换行，闭包没有显式声明参数的，大括号左右都要留空格：

```swift
let value = numbers
    .map { $0 * 2 }
    .filter { $0 > 50 }
    .map { $0 + 10 }
```

如果闭包中的某个参数的类型是显而易见的，那么可以避免声明类型。如果闭包内容语义简单，参数名称可以简写为 `$0`, `$1`, `$2 ` 等。

```swift
doSomethingWithClosure() { response in
    print(response)
}
[1, 2, 3].flatMap { String($0) }
```

在参数列表中，如果是使用了捕获变量或者声明了非 `Void` 返回值，那么应该将参数列表写在一个圆括号里，其他情况下则可以省略圆括号。

```swift
doSomethingWithClosure() { [weak self] (response: NSURLResponse) in
    self?.handleResponse(response)
}

doSomethingWithClosure() { (response) -> String in
    return String(response)
}
```

对于编译器提示的没有非 `Void` 返回值然而有圆括号的情况应该手动删除圆括号。

**Preferred**

```swift
tableView.snp_makeConstraints { make in
    make.edges.equalTo(0)
}
```

**Not Preferred**

```swift
tableView.snp_makeConstraints { (make) in
    make.edges.equalTo(0)
}
```

如果你是将闭包声明为一个类型，那么除非该类型为 Optional 或者该闭包是另一个闭包的参数，否则不需要使用圆括号进行包裹。不过需要用圆括号来标注参数列表，并且使用 `Void` 来指明没有任何结果返回。

```swift
let completionBlock: (success: Bool) -> Void = {
    print("Success? \(success)")
}
let completionBlock: () -> Void = {
    print("Completed!")
}
let completionBlock: (() -> Void)? = nil
```

### 类型

尽可能使用 Swift 原生类型。Swift 提供到 Objective-C 类型的桥接，所以仍然可以使用许多需要的方法。

**Preferred:**

```swift
let width = 120.0                                    // Double
let widthString = (width as NSNumber).stringValue    // String
```

**Not Preferred:**

```swift
let width: NSNumber = 120.0                          // NSNumber
let widthString: NSString = width.stringValue        // NSString
```

#### 常量

常量定义使用 `let` 关键字，变量定义使用 `var` 关键字，如果变量的值不需要改变，请尽量使用 `let` 关键字。可以先使用 `let` 定义任何东西，只有在编译器告诉我们值需要改变的时候才改成 `var` 定义。

使用 `static let` 将常量定义为类属性而不是实例属性，定义为类属性而不是全局常量是因为在实际运用中类属性不会和局部变量和实例属性混淆。所有的类常量需要被包含在一个 `enum`  容器中（不可初始化，比 `class` 和 `struct` 好）。且该容器名是个单数（ 用 `Constant`  而不是  `Constants`）且能表示它是个常量容器，如果不能明确表示时给它加上 `Constant` 后缀。

```swift
enum AccessibilityIdentifier {
    static let pirateButton = "pirateButton"
}
enum ColorConstant {
    static let white = UIClor.white
}
static let shared = MyClassName()
```

#### 可选类型

当我们命名一个可选变量和属性时，避免使用诸如 `optionalString` 和 `maybeView` 这样的命名，因为可选值的表达已经在类型定义中了。

一次性可以操作多个可选值绑定，避免太多 if 语句嵌套：

```swift
var subview: UIView?
var volume: Double?

if let subview = subview, let volume = volume {
    // do something with unwrapped subview and volume
}
```

只应该在 `@IBOutlet` 和依赖注入中使隐式解包。否则其他情况下就应该使用非可选值或者正常的可选值类型变量。虽然有时候你能保证某个变量肯定非 `nil` ，不过这样用的话还是比较安全并且能保证上下一致性。

注: [隐式解包 OPTIONAL](http://swifter.tips/implicitly-optional/)

如果你只是打算判断存放在 Optional 中的值是否为空，那么你应该直接与 `nil` 进行判断而不是使用 `if let` 语句将值取出来。

可以将 `unowned` 当做对于 `weak` 变量的隐式解包，Apple 给我们的建议是如果能够确定在访问时被捕获对象不会已被释放的话，尽量使用 `unowned` ，如果存在被释放的可能，那就选择用`weak`。实际运用中一般非异步操作的时候不存在被捕获对象提前销毁的风险，此时可以使用 `unowned`， 其他时候使用 `weak` 则必须进行 [weak-strong dance](https://bestswifter.com/strong-weak-dance/) 处理。

weak-strong dance 标准格式如下：

```swift
resource.request().onComplete { [weak self] response in
    guard let strongSelf = self else { 
      return
    }
    let model = strongSelf.updateModel(response)
    strongSelf.updateUI(model)
}
```

注：[内存管理，WEAK 和 UNOWNED](http://swifter.tips/retain-cycle/)

当对可选值进行解包的时候，使用与可选值变量一致的变量名

```swift
guard let myValue = myValue else {
   return
}
```
#### 类型推断

使用更加紧凑的代码，让编译器能够推断出常量和变量的类型，类型推断对非空数组和字典适用。需要定义一个特定的类型(比如 `CGFloat` 和 `Int16` )的时候需要明确指定。

**Preferred:**

```swift
let message = "Click the button"
let currentBounds = computeViewBounds()
var names = ["Mic", "Sam", "Christine"]
let maximumWidth: CGFloat = 106.5
```

**Not Preferred:**

```swift
let message: String = "Click the button"
let currentBounds: CGRect = computeViewBounds()
let names = [String]()
```

**空数组和空字典需要明确的类型声明**

对于空数组和空字典，使用类型声明（对于有大量、多行字符的数组和字典也要使用类型声明）。

**Preferred:**

```swift
var names: [String] = []
var lookup: [String: Int] = [:]
```

**Not Preferred:**

```swift
var names = [String]()
var lookup = [String: Int]()
```

注：这条 issue: [Reconsidering empty array and dictionary initialization](https://github.com/raywenderlich/swift-style-guide/issues/143) 有此规则的讨论

### 访问控制

私有属性或者方法需要明确的标明 `private`。除了像 `@IBAction` 和 `@IBOutlet` 的静态说明符之外，`private` 都应该在其他的属性说明符前面。

**Preferred:**

```swift
class TimeMachine {  
    private dynamic lazy var fluxCapacitor = FluxCapacitor()
}
```

**Not Preferred:**

```swift
class TimeMachine {  
    lazy dynamic private var fluxCapacitor = FluxCapacitor()
}
```

属性必须是 `internal` 的才能在单元测试中用 `@testable import ModuleName` 取到。如果属性本来是 `private` 的需要声明为 `internal`，则在属性备注下添加一行 `- warning:` 

```swift
/**
 This property defines the pirate's name.
 - warning: Not `private` for `@testable`.
 */
let pirateName = "LeChuck"	
```

### 控制流

对枚举优先使用譬如 `case 1, 2, 3:` 这样的列表表达式而不是使用 `fallthrough` 关键字。

推荐循环使用 `for-in` 表达式，而不使用 `while` 表达式。

```swift
for _ in 0..<3 {
    print("Hello three times")
}

for (index, person) in attendeeList.enumerate() {
    print("\(person) is at position #\(index)")
}

for index in stride(from: 0, to: item.count, by: 2) {
    print(index)
}

for index in (0...3).reverse() {
    print(index)
}
```

#### 集合操作

尽可能地使用 `map`, `filter`, `reduce` 的组合来进行集合的转换等操作，并且尽可能地避免使用带有副作用的闭包。

**Preferred:**

```swift
let stringOfInts = [1, 2, 3].flatMap { String($0) }
let evenNumbers = [4, 8, 15, 16, 23, 42].filter { $0 % 2 == 0 }
```

**Not Preferred:**

```swift
var stringOfInts: [String] = []
for integer in [1, 2, 3] {
    stringOfInts.append(String(integer))
}

var evenNumbers: [Int] = []
for integer in [4, 8, 15, 16, 23, 42] {
    if integer % 2 == 0 {
        evenNumbers(integer)
    }
}
```

### 风格

#### 正确性

将警告当做错误处理，比如不使用 `++` 或者 `--` 和 C 语言风格的循环，或者用字符串生成方法选择器。

#### 属性命名

控件不要使用缩写，且控件具体类型放在命名的最后。如 UILabel 命名为 xxxLabel，UIButton 命名为 xxxButton。

控制器不要简写为 `VC`。普通 UIViewController 一般命名为 xxxViewController，变量名太长时也可为 xxxxxxxxxController，对于 UIViewController 的子类来说，命名必须明确的指出完整类型，如xxxTableViewController。

不是很明显的类型需要将类型信息包含在属性名中。

```swift
class ConnectionTableViewCell: UITableViewCell {
    let personImageView: UIImageView
    let firstName: String
    let animationDuration: NSTimeInterval
    let popupController: UIViewController
    let popupViewController: UIViewController
    let popupTableViewController: UITableViewController
    
    @IBOutlet weak var submitButton: UIButton!
    @IBOutlet weak var emailTextField: UITextField!
    @IBOutlet weak var nameLabel: UILabel!
}
```

#### 结构体构造器

使用原生的 Swift 结构体构造器，比老式的几何类的构造器要好。

推荐做法：

```swift
let bounds = CGRect(x: 40, y: 20, width: 120, height: 80)
let centerPoint = CGPoint(x: 96, y: 42)
```

不推荐做法：

```swift
let bounds = CGRectMake(40, 20, 120, 80)
let centerPoint = CGPointMake(96, 42)
```

推荐使用结构体限定的常量 `CGRect.infiniteRect`，`CGRect.nullRect`，`CGRect.zero` 等，来替代全局常量 `CGRectInfinite`，`CGRectNull`，`CGRectZero` 等。

#### 空格

采用 4 个空格的缩进风格。

方法定义的大括号或者其他大括号（`if`、`else`、`switch`、`while` 等）—— 般都放在定义名称的同一行，并且使用一个新的行来结束。

```swift
if someBoolean {
    // do something
} else {
    // do something else
}
```

提示：你可以通过以下方法重新进行缩进：选择一些代码（或者使用 ⌘A 选择所有），然后按 Control-I (或者点击菜单栏 Editor\Structure\Re-Indent）。

应该在方法之间空出一行，从视觉上有更好的区分和组织。方法内的空白行隔开不同的功能，但是当一个方法中有很多段落时应该将该方法重构成几个方法。

冒号的左边总是没有空格右边总是有空格。当它存在于三目运算 `? :` 或者空字典 `[:]` 里面时是个例外。

```swift
class TestDatabase: Database {
    var data: [String: CGFloat] = ["A": 1.2, "B": 3.2]
    var tmp = 2 > 1 ? true : false
}
```

#### 分号

Swift 不需要在你代码中的每一句表达式之后添加分号。只有在你需要在一行中连接多个表达式中，使用分号来区隔。不要在同一行编写多个使用分号区隔的表达式。

#### 圆括号

Swift 中条件语句的条件不需要圆括号包围。

#### 语法糖

推荐使用类型定义简洁的版本，而不是全称通用语法。

**Preferred:**

```swift
var deviceModels: [String]
var employees: [Int: String]
var faxNumber: Int?
```

**Not Preferred:**

```swift
var deviceModels: Array<String>
var employees: Dictionary<Int, String>
var faxNumber: Optional<Int>
```

#### 隐式成员表达式

避免在使用 enum 的时候写出全名。

**Preferred:**

```swift
imageView.setImageWithURL(url, type: .person)
```

**Not Preferred:**

```swift
imageView.setImageWithURL(url, type: AsyncImageView.Type.person)
```

在写类方法的时候不用简短写法，应该使用类名.方法名。否则编译器无法提示且可读性差。

**Preferred:**

```swift
imageView.backgroundColor = UIColor.whiteColor()
```

**Not Preferred:**

```swift
imageView.backgroundColor = .whiteColor()
```

注：[Implicit Member Expression](https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/Expressions.html#//apple_ref/doc/uid/TP40014097-CH32-ID394)

#### Guard 关键字

`guard` 语句不要和 `return` 放在同一行。代码嵌套度高时使用 `guard` 提早退出降低代码嵌套度。

**Preferred:**

```swift
func computeFFT(context: Context?, inputData: InputData?) throws -> Frequencies {
    guard let context = context else { 
    	throw FFTError.noContext
    }
    guard let inputData = inputData else { 
    	throw FFTError.noInputData
    }
    return frequencies
}
```

**Not Preferred:**

```swift
func computeFFT(context: Context?, inputData: InputData?) throws -> Frequencies {
    if let context = context {
        if let inputData = inputData {
            return frequencies
        } else {
            throw FFTError.noInputData
        }
    } else {
        throw FFTError.noContext
    }
}
```

`guard `状态必须退出，通常情况下退出语句是像 `return`, `throw`, `break`, `continue `和 `fatalError()` 这样简单的一行代码，大的代码块需要避免。如果在多个出口退出时都想执行清理代码，可以使用 `defer` 代码块避免出现多个清理代码。

### 注释

属性注释需要用 `///`，方便生成文档和 Option键 + 左键查看注释。虽然 `//` 也被视为注释，但是这种语法会被 Xcode 忽略，而不产生对应的代码文档，所以尽量只在各种代码块中可以使用 `//` 来注释。

`//` 注释时不要手动换行。

`//`，`///` 后面总是要跟上一个空格。

注：[在 Xcode 中使用 Markdown 生成 Swift 代码文档](http://swift.gg/2016/06/15/swift-markdown/)

## **API Design Guidelines**

### API 命名

#### 提倡清晰的用法

- 包含所有必需的词组以避免歧义，当人们读代码的时候，命名就显得十分重要。

**Preferred:**

```swift
extension List {
    public mutating func remove(at position: Index) -> Element
}
employees.remove(at: x)
```

**Not Preferred:**

```swift
extension List {
    func remove(_ position: Index) -> Element
}
employees.remove(x) // unclear: are we removing x?
```

- **省略多余的词组**。命名中的每一个词组都应该表达关于使用方法的重要信息。

**Preferred:**

```swift
public mutating func remove(_ member: Element) -> Element?
allViews.remove(cancelButton) // clearer    
```

**Not Preferred:**

```swift
public mutating func removeElement(_ member: Element) -> Element?
allViews.removeElement(cancelButton)
```

- 变量、参数、关联类型依据作用对其进行命名，而不是基于它们的类型。

**Preferred:**

```swift
var greeting = "Hello"
protocol ViewController {
    associatedtype ContentView : View
}
class ProductionLine {
    func restock(from supplier: WidgetFactory)
}
```

**Not Preferred:**

```swift
var string = "Hello"
protocol ViewController {
    associatedtype ViewType : View
}
class ProductionLine {
    func restock(from widgetFactory: WidgetFactory)
}
```

如果某个关联类型和它的协议联系非常紧密，导致它的作用就是它的协议名，那就给关联类型的名字加上 `Type` 避免冲突：

> ```swift
> protocol Sequence {
>     associatedtype IteratorType : Iterator
> }
> ```

- 对弱类型信息进行补充使其可以清晰描述参数的作用。

当参数类型是弱类型，尤其是 `NSObject`、 `Any`、`AnyObject` 或者是诸如 `Int`、`String ` 之类的基本类型的时候，调用处的类型信息和上下文环境可能无法完全表明函数意图。

**Preferred:**

```swift
func addObserver(_ observer: NSObject, forKeyPath path: String)
grid.addObserver(self, forKeyPath: graphics) // clear
```

**Not Preferred:**

```swift
func add(_ observer: NSObject, for keyPath: String)
grid.add(self, for: graphics) // vague
```

#### 尽量流利的使用

- 工厂方法以 `make` 为前缀。

```swift
x.makeIterator()
```

- 构造器和工厂方法调用时应由一个不包含第一实参的短语构成。

**Preferred:**

```swift
let foreground = Color(red: 32, green: 64, blue: 128)
let newPart = factory.makeWidget(gears: 42, spindles: 14)
```

而下面这段代码，API 作者试图用第一实参创建符语法连续性的 API（构造方法短语包含了第一实参）：

**Not Preferred:**

```swift
let foreground = Color(havingRGBValuesRed: 32, green: 64, andBlue: 128)
let newPart = factory.makeWidget(havingGearCount: 42, andSpindleCount: 14)
```

- **根据方法和函数的副作用为它们命名**。

  - 没有副作用的用名词短语命名：

  ```swift
  x.distance(to: y)
  i.successor()
  ```

  - 有副作用的用祈使动词短语命名：

  ```swift
  print(x)
  x.sort()
  x.append(y)
  ```

  - Mutating 和 Nonmutating 方法名应该保持一致性。一个 Mutating 方法通常有个语义上类似的 Nonmutating 变体。

    - 当操作使用动词描述的时候，Mutating 方法用该动词的祈使语气做方法名，Nonmutating 方法为对该动词加 `ed`、`ing` 后缀。

    | Mutating      | Nonmutating          |
    | ------------- | -------------------- |
    | `x.sort()`    | `z = x.sorted()`     |
    | `x.append(y)` | `z = x.appending(y)` |

    当动词后不跟直接宾语时用 `ed`，有直接宾语时用 `ing` 才符合语法：

    ```swift
    funcreversed() -> Self
    funcstrippingNewlines() -> String                      
    ```

    - 当操作使用名词描述的时候，Nonmutating 方法用该名词做方法名，Mutating 方法为对该名词加 `from` 前缀。

    | Nonmutating          | Mutating              |
    | -------------------- | :-------------------- |
    | `x = y.union(z)`     | `y.formUnion(z)`      |
    | `j = c.successor(i)` | `c.formSuccessor(&i)` |

- Nonmutating 的 Bool 属性和返回 Bool 值的方法读起来应该像是断言：

```swift
x.isEmpty
line1.intersects(line2)
```

### 约定

#### 一般约定

- 优先考虑方法和属性，而不是自由函数。自由函数只在几种特殊情况下才能使用：

  - 当没有明显的 `self` 对象的时候：

  ```swift
  min(x, y, z)
  ```

  - 当函数是一个不受约束的泛型的时候：

  ```swift
  print(x)
  ```

  - 当函数语法是某个领域中公认的符号时：

  ```swift
  sin(x)
  ```

- 当多个方法拥有相同的基础含义的时候，可以使用相同的名字重载，特别是对于有不同的参数类型，或者在不同的作用域范围内的方法。但要避免返回类型的重载，因为这会导致在类型推断的时候出现歧义。

#### 参数

- 充分利用参数默认值，这样可以简化常用的操作。一般情况下，如果一个参数经常使用某一个值的话，那么可以考虑将这个值设置为默认值。

默认参数通过隐藏不相关的信息提高了方法的可读性。

**Preferred:**

```swift
let order = lastName.compare(royalFamilyName)
```

**Not Preferred:**

```swift
let order = lastName.compare(royalFamilyName, options: [], range: nil, locale: nil)
```

- 最好将带有默认值的参数放在参数列表的最后面。不带默认值的参数对于方法来说更重要，并且当方法调用的时候可以提供一个稳定的初始化范式。

#### 参数标签（参数外部名）

在 Swift 3 下，一个方法所接受的参数必须拥有参数标签，如果依然想参数没有参数标签，那么可以使用单个下划线作为允许匿名符号。

- **当不同参数不能被有效区分时，删除所有参数标签**。

```swift
min(number1, number2)
zip(sequence1, sequence2)
```

- **当初始化器做无损类型转换的时候，删除第一个参数标签**。

第一个参数总应该是要被转换的东西：

```swift
extension String {
    // Convert `x` into its textual representation in the given radix
    init(_ x: BigInt, radix: Int = 10)   ← 注意初始的下划线
}

text = "The value is: "
text += String(veryLargeNumber)
text += " and in hexadecimal, it's"
text += String(veryLargeNumber, radix: 16)
```

对于有损类型的转换，推荐使用参数标签来描述这个特定类型：

> “无损类型转换”的意思是，对于执行类型转换（参数是待转换的类型，构造器所在的类是要转换的目标类型）的构造器来说，“无损”意味着待转换类型的存储空间小于等于目标类型所占用的存储空间，比如说 `Int32` 转换为 `Int64`，编译器直接将 `Int32` 放到 `Int64` 所在的内存当中，不足的部分会自动用 `0` 补齐。
>
> 同理，“有损转换”就意味着编译器需要删除待转换类型多余的空间以便存放到目标类型当中，比如说 `Int64` 转换为 `Int32`，编译器会将 `Int64` 多余的32位数据砍掉，才能放到 `Int32`当中。

```swift
extension UInt32 {
    init(_ value: Int16)            ← 保值类型转换，所以没有标签
    init(truncating source: UInt64) ← 有损类型转换，所以有标签
    init(saturating valueToApproximate: UInt64)
}
```

- **当第一个参数是介词短语的一部分时，应设置参数标签**。这时参数标签一般以介词开头。

```swift
x.removeBoxes(havingLength: 12)
```

当头两个参数代表一个抽象的整体时是个例外，在这种情况下，参数标签应在介词之后，进而保证抽象概念清晰：

**Preferred:**

```swift
a.moveTo(x: b, y: c)
a.fadeFrom(red: b, green: c, blue: d)
```

**Not Preferred:**

```swift
a.move(toX: b, y: c)
a.fade(fromRed: b, green: c, blue: d)
```

- 如果第一个参数形式是符合语法规范的短语的一部分，删除它的参数标签，可在方法名后加上短语的前缀词。

```swift
x.addSubview(y)
```

那么第一个参数不是符合语法的短语的部分时它应该有一个参数标签：

```swift
view.dismiss(animated: false)
let text = words.split(maxSplits: 12)
let studentsByName = students.sorted(isOrderedBefore: Student.namePrecedes)
```

默认参数是可以被省略不写的，在这种情况下它们不能和方法名组成一个符合语法规范的短语，所以它们总是应该有标签。

```swift
extension Document {
    func close(completionHandler completion: ((Bool) -> Void)? = nil)
}
doc1.close()
doc2.close(completionHandler: app.quit)
```

如果您省略了参数标签的话，语句调用就可能会出现歧义，它可能会将参数认做是"语句"的直接宾语：

```swift
extension Document {
    func close(completion: ((Bool) -> Void)? = nil)
}
doc.close(app.quit)              // 是要关闭这个 app.quit 函数 ？
```

如果您将此外部参数名放到方法名当中的话（试图组成符合语法规范的短语，删除参数标签），当使用默认值的时候就会变得很诡异：

```swift
extension Document {
    func closeWithCompletionHandler(completion: ((Bool) -> Void)? = nil)
}
doc.closeWithCompletionHandler()   // 完成后处理什么呢 ？
```

- **给其它所有参数都加上参数标签**



## **目录命名和文件结构**

### 目录命名

- 文件名不用单词缩写。

- 文件名采用帕斯卡命名法，第一个单词首字母采用大写字母，后续单字的首字母亦用大写字母。

- Swift 中实现了类似命名空间的功能，所以不需要写类名前缀，只要保证当前 target 内无重复使用的类名即可。

- 普通的视图控制器（如 `UIViewController`，`UITableViewController`，`UICollectionViewController`）一般以 viewController 作为后缀，但是文件名过长时可以省略 view，其他控制器可以使用自身类型作为后缀（如 `UINavigationController`，`UITabBarController` 分别用 `navigationController`，`tabBarController` 做后缀）。

- Swift 中扩展没有名字，扩展文件的文件名就跟 Object-C 保持一致使用 `类型+功能` 方式，如 `UIKit+Rx`。不要使用 `类型+Extension` 这种一个文件包含全部扩展功能的命名。

- MVVM 中 `V` 和 `VM` 命名应该一致，如 `LoginViewController`，`LoginViewModel`。


### 文件结构

#### 类型外部结构

1. Import
2. typealias 重命名
3. 定义闭包
4. 定义枚举、结构体、协议

#### 类型内部结构

如果一组方法联系密切，将它们放在同一个扩展中并用 `// MARK: -` 注释，如生命周期，点击事件等。

注：[Using Swift Extensions The “Wrong” Way](https://www.natashatherobot.com/using-swift-extensions/)，翻译：[使用Swift扩展的“错误”方式](http://geek.csdn.net/news/detail/67296)

1. 嵌套类型

2. @IBOutlet 属性（可以通过 didSet 给控件赋值）

3. 公有属性

   - 存储属性
   - 计算属性
   - 属性观察器
   - 通过闭包和函数来初始化属性

   ```swift
   let someProperty: SomeType = {
       // 在这个闭包中给 someProperty 创建一个默认值
       // someValue 必须和 SomeType 类型相同
       return someValue
   }()
   ```

   - 懒加载属性

   ```swift
   lazy var imagePicker: UIImagePickerController = {
       let imagePicker = UIImagePickerController()
       imagePicker.delegate = self
       imagePicker.allowsEditing = false
       return imagePicker
   }()  
   ```

4. 私有属性（细分见上公有属性）

5. 生命周期

6. setup 方法

7. action 方法

8. 网络请求或请求回调（VM 中为请求，V 中就是请求回调）

9. 实现系统协议和自定义协议

10. private 方法

   比较通用的私有方法单独提出到一个 `private extension` 中且不用再加 `private` 标明，但如果私有方法只跟某个功能模块或方法相关，则它们可以使用嵌套函数。

#### 私有嵌套类型

尽量少用文件内的 `private` 属性，可以通过**私有嵌套类型**来实现类似的功能还能避免命名空间污染。私有嵌套类型能在当前类型中使用而 `private` 属性能在当前文件中使用。

```swift
// private var DescriptiveName = "nsh_DescriptiveName"

extension UIViewController {
    private enum AssociatedKeys {
        static var DescriptiveName = "nsh_DescriptiveName"
    }

    var descriptiveName: String? {
        get {
            return objc_getAssociatedObject(self, &AssociatedKeys.DescriptiveName) as? String
        }
        set {
            if let newValue = newValue {
                objc_setAssociatedObject(
                    self,
                    &AssociatedKeys.DescriptiveName,
                    newValue as NSString?,
                    UInt(OBJC_ASSOCIATION_RETAIN_NONATOMIC)
                )
            }
        }
    }
}
```

## **参考**

- [raywenderlich](https://github.com/raywenderlich)/[**swift-style-guide**](https://github.com/raywenderlich/swift-style-guide)


- [linkedin](https://github.com/linkedin)/[**swift-style-guide**](https://github.com/linkedin/swift-style-guide)

- [API Design Guidelines](https://swift.org/documentation/api-design-guidelines/)