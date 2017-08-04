# Interfaces: like abstract base classes
```c
interfaceName = interface +j +o {
    const constantA: i32 = 10;

    methodA(argumentA: i32): returnType;
    methodB();

    static staticMethod(): returnType;
}
```
- Create an interface in Java (+j) and Objective-C (+o), called by C++. Java and Obj-C implement the methods.

```c
interfaceName = interface +c {
    const constantA: i32 = 10;

    methodA(argumentA: i32): returnType;
    methodB();
    const methodC(): returnType;

    static staticMethod(): returnType;
}
```
- Create an interface in C++ (+c)), called by Java and Obj-C. C++ implement the methods.

# Records: like structs
```c
recordName = record {
    attributeA: typeA;
    attributeB: typeB;
    attributeC: string;
} deriving (eq, ord)
```
- Create a record with equality comparison (eq) and ordering comparison (ord)

# Enums: like scoped enums
```c
enumName = enum {
    optionA;
    optionB;
    optionC;
}
```
# Data types:

| Data Type         |      Syntax          | C++ | Java | Obj-C |
|-------------------|----------------------|-----|------|-------|
|Boolean            |bool|bool|boolean|BOOL|
|Primitives         |i8,i16,i32,i64,f32,f64|
|Strings            |string|std::string|String|NSString|
|Binary             |binary|std::vector<uint8_t>|byte[]|NSData|
|Date               |date|chrono::system_clock::time_point|Date|NSDate|
|List               |list&lt;type>|std::vector<T>|ArrayList|NSArray|
|Set                |set&lt;type>|std::unordered_set<T>|HashSet|NSSet|
|Map                |map<typeA, typeB>|std::unordered_map<K,V>|HashMap|NSDictionary|
|Optionals          |optional&lt;typeA>|std::experimental::optional<T>|object / boxed primitive reference|object / NSNumber strong reference|

<!-- anchor -->

<center>
<br><br>
Copyright © 2017 Alex Choi
</center>
