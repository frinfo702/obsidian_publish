- 新しいオブジェクトの設計図
- プロパティとメソッドをひとまとめに
```ts
class Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    greet() {
        return `こんにちは、${this.name}です。`;
    }
}

const person1 = new Person("太郎");
console.log(person1.greet()); // "こんにちは、太郎です。"
```
- `cunstructor`で初期化を行う

## アクセス修飾子
- クラスの外部kららのアクセスを制限しカプセル化
	- `public`どこからでもアクセス可能
	- `private`クラス内からのみアクセス可能
	- `protected`クラス内とサブクラスからアクセス可能


```ts
class Person {
    private name: string;

    constructor(name: string) {
        this.name = name;
    }

    public greet() {
        return `こんにちは、${this.name}です。`;
    }
}
```

## 継承
```ts
class Employee extends Person {
    private department: string;

    constructor(name: string, department: string){
        super(name); // 親クラスのconstructorを呼び出す
        this.department = department;

    }
    public greet(){
        return `${super.greet()} 私は${this.department}部門の所属です`;

    }
}
const employee1 = new Employee("華子", "IT");
console.log(employee1.greet());
```

> [!NOTE]
> 基本的には`pribate`を使うのがTSっぽい