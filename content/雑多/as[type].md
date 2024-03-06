- `as`キーワードは型アサーションに使用される
- 値が自動的に推論できない時に明示的に知らせる

例
```ts
let someValue: any = "Hello, TypeScript!";
let strLength: number = (someValue as string).length

console.log(strLength); // outputs: 18
```

```ts
interface Cat {
  meow: number;
}

let pet: any = { meow: 5 };

// petをCatインターフェースとして扱いたい場合
let catPet = pet as Cat;

console.log(catPet.meow); // 5
```
- pen変数はany型なので型システムはpetの具体的な構造がわからないが、as Catを使うことでCat インターフェースのインスタンスとして扱うことができる
- catPet.meowに安全にアクセスできる
- コンパイラはmeowプロパティの存在を保証する

> [!NOTE]
> as [type]は型アサーションであり具体的な型に変数を強制的にキャストする際に使う

