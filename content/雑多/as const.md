- リストの各要素に対しても読み取り専用の属性を付加

- `const numbers = [1, 2, 3]`とした場合
	- `numbers = [4, 5, 6]`はできない
	- `numbers[0] = -1`はできる
- `const numbers = [1, 2, 3] as const`の場合
	- `numbers = [4, 5, 6]`はできない 
	- **`numbers[0] = -1`これもできない




>[!NOTE]
> as constをつけると配列の長さや各要素に対しても不変として扱われる

