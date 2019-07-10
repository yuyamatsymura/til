## 変数についての問題で間違えていたところ(記録用：紫本41,42)

```java
class Foo {
	String str = "hello";
}
class Main{
	public static void main(String[] args) {
		Foo obj;
	}
}
```

Fooクラスの型のobjという参照型の変数ができる
コードの追加
```
System.out.println(obj.str);
```

```java
class Foo {
	String str = "hello";
}
class Main{
	public static void main(String[] args) {
		Foo obj;
		System.out.println(obj.str);
	}
}
```

コンパイルエラーになる

```
C:\java_src>javac Test.java
Test.java:8: エラー: 変数objは初期化されていない可能性があります
        System.out.println(obj.str);
                           ^
エラー1個
```

理由は初期化されておらず参照先がわからないため

変数宣言をするとき初期化をnullでしてみる

```java
Foo obj = null;
```

初期化をすればコンパイルができる
しかし参照先がnullのため実行できない

NullPointerExceptionエラーが発生する

*Fooクラスの変数を使用する場合はインスタンス化するか*
*static変数を使用する方法がある*

### インスタンス化パターン
```java
class Foo {
	String str = "hello";
}

class Test {
    public static void main(String[] args) {
    	Foo obj1 = new Foo();
    	Foo obj = obj1;
    	System.out.println(obj.str);
    }
}
```
コンパイル、実行ともに成功する

```
C:\java_src>java Test
hello
```



### static変数を使用するパターン
```java
class Foo {
	static String str = "hello";
}

class Test {
    public static void main(String[] args) {
    	static Foo obj;
    	System.out.println(obj.str);
    }
}
```
コンパイル、実行ともに成功する

```
C:\java_src>java Test
hello
```
