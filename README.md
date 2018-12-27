# this is a project for mysql notes


## 数据类型
### Enum type
enum('a','b','c')  枚举类型，单选，本质是字符串,insert非法字符会提示data truncated error
### Set type
set(1,2,3) 同上多选
### 日期
mysql 日期分为date YYYY-MM-DD,time HH:MM:SS,year YYYY三种
此外还有datetime（date+time）、timestamp，前者略，后者比datetime范围要小，从1900到2038
mysql的日期允许用不严格的语法，'98/01/01'这种直接写入,并且可以用任何字符分隔，如98@01@01等，另外两位的年份会按照00-69范围的年值转换为2000-2069。 o 70-99范围的年值转换为1970-1999,非常有趣
### int
int类型在mysql中被区分为了tiny small medium int bigint，分别对应1,2,3,4,8字节长度存储
### 定点
numeric和decimal在mysql中是同一种类型，且数值小数位超长，四舍五入，如果四舍五入导致整数超长才会抛异常
### 浮点
real是一种可以配置的浮点类型，默认它与double相同，可以设置real_as_float属性来制定它和float相同
### bit
二进制数据，直接存1010，与sqlserver不同的是mysql的二进制数据类型可以指定长度
