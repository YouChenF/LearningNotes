
# 工作框架

## 划分词素(lexeme)
扫描字符列表，将它们归纳为具有某些含义的最小序列，每一组字符都被称为词素，例子如下：
> 字符串："var age = 18;"
> 划分为词素：var  age  =  18  ;

## 定义标记(token)
将词素与其他信息组合在一起称为一个标记(token)：
- 标记类型(token type)
- 词素(lexeme)
- 字面量(literatual)
- 位置信息(line)


## 识别词素(lexeme)
将字符分组为词素的规则被称为它的词法语法，词法语法可以使用正则语言进行表示。尽管可以使用正则语言去识别词素，在本项目中，我们手动实现识别词素。

## 组装标记(token)
将词素转换为标记，并输出。


# 关键实现
**设置字符串偏移量**
	
		private int start = 0;
		private int current = 0;
	`start`字段指向被扫描的词素中的第一个字符，`current`字段指向当前正在处理的字符。

**获取源文件中的下一个字符**
	
		private char advance() {
	    current++;
	    return source.charAt(current - 1);
		  }

**添加tokens**
	
		private void addToken(TokenType type) {
	    addToken(type, null);
		  }
		  private void addToken(TokenType type, Object literal) {
	    String text = source.substring(start, current);
	    tokens.add(new Token(type, text, literal, line));
		  }