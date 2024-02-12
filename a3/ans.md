### (a)

![image-20240106155840590](/Users/bowieshi/Library/Application Support/typora-user-images/image-20240106155840590.png)

[ROOT, parsed, this] | [sentence, correctly] | | SHIFT

[ROOT, parsed, this, sentence] | [correctly] | | SHIFT

[ROOT, parsed, sentence] | [correctly] | sentence -> this | LEFT-ARC

[ROOT, parsed] | [correctly] | parsed -> sentenced | RIGHT-ARC

[ROOT, parsed, correctly] | [] | | SHIFT

[ROOT, parsed] | [] | parsed -> correctly | RIGHT-ARC

[ROOT] | [] | ROOT -> parsed | RIGHT-ARC

### (b)

2n

