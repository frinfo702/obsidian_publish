- HDLを用いて回路のアーキテクチャを設計し、最適化を考えれる
- ハードウェアシュミレータというソフトウェアツールを使う
- メモリ上にプログラム通りの回路を構成してテストできる
- 回路版デバッグ
例：XORゲートの構成
```HDL
CHIP Xor {
	IN a, b;
	OUT out;
	PARTS:
	Not(in=a, out=nota);
	Not(in=b, out=notb);
	And(a=a, b=notb, out=w1);
	And(a=nota, b=b, out=w2);
	Or(a=w1, b=w2, out=out);
}
```

テストスクリプト
```tst
load Xor.hdl,
output-list a, b, out;
set a 0, set b 0,
eval, output/;
set a 0j, set b 1,
eval, output;
set a 1, set b 0,
eval, output;
set a 1, set b 1,
eval, output;
```
