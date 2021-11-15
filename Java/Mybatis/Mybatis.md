# Mybatis

### select Attributrid
| 属性 |	描述 |
| ---- | ---- |
| id | 	在命名空间中唯一的标识符,可以被用来引用这条语句。|
| parameterType | 	将会传入这条语句的参数类的完全限定名或别名。|
| parameterMap | 	这是引用外部 parameterMap 的已经被废弃的方法。使用内联参数映射和 parameterType 属性。|
| resultType | 	从这条语句中返回的期望类型的类的完全限定名或别名。注意集合情形,那应该是集合可以包含的类型,而不能是集合本身。使用  resultType 或 resultMap,但不能同时使用。|
| resultMap | 	命名引用外部的 resultMap。返回 map 是 MyBatis 最具力量的特性, 对其有一个很好的理解的话, 许多复杂映射的情形就能被解决了。使用 resultMap 或 resultType,但不能同时使用。|
| flushCache | 	将其设置为 true,不论语句什么时候被带哦用,都会导致缓存被清空。默认值:false。|
| useCache | 	将其设置为 true, 将会导致本条语句的结果被缓存。默认值: true。|
| timeout | 	这个设置驱动程序等待数据库返回请求结果,并抛出异常时间的最大等待值。默认不设置(驱动自行处理)|
| fetchSize | 	这是暗示驱动程序每次批量返回的结果行数。默认不设置(驱动自行处理)。|
| statementType | 	STA TEMENT,PREPARED 或 CALLABLE 的一种。这会让 MyBatis 使用选择使用 Statement,PreparedStatement 或 CallableStatement。默认值:PREPARED。 |
| resultSetType | 	FORWARD_ONLY|SCROLL_SENSITIVE|SCROLL_INSENSITIVE 中的一种。默认是不设置(驱动自行处理)。 |
| databaseId | 	In case there is a configured databaseIdProvider, MyBatis will load all statements with no databaseId attribute or with a databaseId that matches the current one. If case the same statement if found with and without the databaseId the latter will be discarded.  |


### JDBC type
```
JDBC Type           Java Type
CHAR                String
VARCHAR             String
LONGVARCHAR         String
NUMERIC             java.math.BigDecimal
DECIMAL             java.math.BigDecimal
BIT                 boolean
BOOLEAN             boolean
TINYINT             byte
SMALLINT            short
INTEGER             INTEGER
BIGINT              long
REAL                float
FLOAT               double
DOUBLE              double
BINARY              byte[]
VARBINARY           byte[]
LONGVARBINARY       byte[]
DATE                java.sql.Date
TIME                java.sql.Time
TIMESTAMP           java.sql.Timestamp
CLOB                Clob
BLOB                Blob
ARRAY               Array
DISTINCT            mapping of underlying type
STRUCT              Struct
REF                 Ref
DATALINK            java.net.URL[color=red][/color]
```
