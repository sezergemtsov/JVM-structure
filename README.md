# JVM-structure

```java
public class JvmComprehension {
```

_В метаспейсе выделена память на дерево связанных классов JvmComprehension_

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
_Если в метаспейсе еще не выделена память  при обработке JvmComprehension на классы связанные с Object то это происходит сейчас_
        
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

_Начало обработки фрейма printAll_
    
```java
        Integer uselessVar = 700;                   // 5
```

_В стеке внутри фрейма printAll создана переменная с именем uselessVar_
_Так же в метаспейсе выделена память на дерево классов Integer_
        
```java
        System.out.println(o.toString() + i + ii);  // 6
    }
}
```
_Создан поток вывода в систему в который переданы значения инициализированных в стеке в фрейме main переменных_
_Закрыты фреймы printAll и далее main_
_Объект o может быть удален из кучи сборщиком мусора_
