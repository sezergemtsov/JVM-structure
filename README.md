# JVM-structure

```java
public class JvmComprehension {
```

_В метаспейсе выделена память на класс JvmComprehension_

```java
    public static void main(String[] args) {
```
    
_В стеке создан фрейм main_
    
```java
        int i = 1;                      // 1
```
        
_В стеке создан примитив с именем i и присвоено значение 1 (указатель стека сдвинулся на него, внутри фрейма все переменные уже инициализированы)_
        
```java
        Object o = new Object();        // 2
```
_В куче создан обьект типа Object по шаблону пустого конструктора, переменной из стека с именем o присвоена ссылка на этот объект в куче_
        
```java
        Integer ii = 2;                 // 3
```
        
_В стеке создан примитив с именем ii и присвоено значение 2_
        
```java
        printAll(o, i, ii);             // 4
```
        
_В стеке внутри фрейма main создан фрейм printAll_

```java
        System.out.println("finished"); // 7
    }
```

```java
    private static void printAll(Object o, int i, Integer ii) {
```
    
```java
        Integer uselessVar = 700;                   // 5
```
        
        
```java
        System.out.println(o.toString() + i + ii);  // 6
    }
}
```
