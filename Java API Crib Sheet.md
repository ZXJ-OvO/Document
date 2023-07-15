# java

## util



### Arrays

#### toString

#### copyOfRange

#### copyOf

#### setAll

#### sort

#### binarySearch

#### equals

#### deepToString



### ArrayList

#### add

#### get

#### size

#### remove

#### contains



### Calendar

#### getInstance

#### get

#### getTime

#### getTimeInMillis

#### set

#### add





### Collection

#### add

#### clear

#### remove

#### contains

#### isEmpty

#### size

#### toArray

#### iterator



### Collections

#### addAll

#### shuffle

#### sort



### Comparator

#### compare

#### comparingInt

#### sort







### Date

#### getTime

### regex

#### Pattern

##### compile

##### matcher

#### Matcher

##### find

##### group





### HashMap

#### put

#### entrySet

#### containsKey



### HashSet

#### add



### Iterator

#### hasNext

#### next



### LinkedHashSet

#### add





### LinkedList

#### addFirst

#### addLast

#### get

#### getFirst

#### getLast

#### removeLast

#### removeFirst



### List

#### add

#### get

#### size

#### remove



### Map

#### put

#### size

#### clear

#### isEmpty

#### get

#### remove

#### containsKey

#### containsValue

#### keySet

#### values

#### keySet

#### get

#### Entry

##### getKey

##### getValue





### Objects

#### equals

#### isNull

#### nonNull





### Random

#### nextInt

#### nextDouble



### Scanner

#### nextInt

#### nextDouble

#### nextLine

#### next





### Set



### Stream

#### stream

#### of

#### filter

#### sorted

#### limit

#### skip

#### distinct

#### map

#### concat

#### forEach

#### count

#### max

#### min

#### collect

#### toArray

#### toList

#### toSet

#### toMap



### StringJoiner

#### add





### TreeSet

#### add

#### pollFirst

## lang

### Comparable

#### CompareTo



### Consumer

#### accept



### Double

#### parseDouble



### Integer

#### parseInt

#### valueOf



### Math

#### abs

#### ceil

#### floor

#### round

#### max

#### pow

#### random





### Runtime

#### getRunTime

#### totalMemory

#### maxMemory

#### exit

#### availableProcessors

#### freeMemory

#### exec





### String

| 构造器                                              | 说明                                                         |
| --------------------------------------------------- | ------------------------------------------------------------ |
| public String()                                     | 创建一个空白字符串对象，不含有任何内容                       |
| public String(String original)                      | 根据传入的字符串内容，来创建字符串对象                       |
| public String(char[] chars)                         | 根据字符数组的内容，来创建字符串对象                         |
| public String(byte[] bytes)                         | 根据字节数组的内容，来创建字符串对象                         |
| String(byte[] bytes)                                | 通过使用平台的默认字符集解码指定的字节数组来构造新的  String |
| String(byte[] bytes, String charsetName)            | 通过指定的字符集解码指定的字节数组来构造新的 String          |
| public String(byte bytes[], int offset, int length) | 配合FileInputStream.read(byte[] byte)使用，读取指定的文件数组中的数据，从offset开始读（通常为0），到length结束 |
|                                                     |                                                              |

| 方法名                                                       | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| public int length()                                          | 获取字符串的长度返回（就是字符个数）                         |
| public char charAt(int index)                                | 获取某个索引位置处的字符返回                                 |
| public char[] toCharArray()：                                | 将当前字符串转换成字符数组返回                               |
| public boolean equals(Object anObject)                       | 判断当前字符串与另一个字符串的内容一样，一样返回true         |
| public boolean equalsIgnoreCase(String anotherString)        | 判断当前字符串与另一个字符串的内容是否一样(忽略大小写)       |
| public String substring(int beginIndex, int endIndex)        | 根据开始和结束索引进行截取，得到新的字符串（包前不包后）     |
| public String substring(int beginIndex)                      | 从传入的索引处截取，截取到末尾，得到新的字符串返回           |
| public String replace(CharSequence target, CharSequence replacement) | 使用新值，将字符串中的旧值替换，得到新的字符串               |
| public boolean contains(CharSequence s)                      | 判断字符串中是否包含了某个字符串                             |
| public boolean startsWith(String prefix)                     | 判断字符串是否以某个字符串内容开头，开头返回true，反之       |
| public String[] split(String regex)                          | 把字符串按照某个字符串内容分割，并返回字符串数组回来         |
| byte[] getBytes()                                            | 使用平台的默认字符集将该 String编码为一系列字节，将结果存储到新的字节数组中 |
| byte[] getBytes(String charsetName)                          | 使用指定的字符集将该 String编码为一系列字节，将结果存储到新的字节数组中 |
|                                                              |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |

#### contains

#### valueOf

#### matches

#### indexOf



### StringBuffer

#### reverse

#### length

#### toString

#### append





### StringBuilder

#### reverse

#### length

#### toString

#### append

#### equals

#### substrin



### System

#### currentTimeMillis

#### exit



## IO

### File

| **构造器**                               | **说明**                                       |
| ---------------------------------------- | ---------------------------------------------- |
| public **File(String pathname)**         | 根据文件路径创建文件对象                       |
| public File(String parent, String child) | 根据父路径和子路径名字创建文件对象             |
| public File(File parent, String child)   | 根据父路径对应文件对象和子路径名字创建文件对象 |

| **方法名称**                   | **说明**                                                     |
| ------------------------------ | ------------------------------------------------------------ |
| public boolean exists()        | 判断当前文件对象，对应的文件路径是否存在，存在返回true       |
| public boolean isFile()        | 判断当前文件对象指代的是否是文件，是文件返回true，反之。     |
| public boolean isDirectory()   | 判断当前文件对象指代的是否是文件夹，是文件夹返回true，反之。 |
| public String getName()        | 获取文件的名称（包含后缀）                                   |
| public long length()           | 获取文件的大小，返回字节个数                                 |
| public long lastModified()     | 获取文件的最后修改时间。                                     |
| public String getPath()        | 获取创建文件对象时，使用的路径                               |
| public boolean createNewFile() | 创建一个新的空的文件                                         |
| public boolean mkdir()         | 只能创建一级文件夹                                           |
| public boolean mkdirs()        | 可以创建多级文件夹                                           |
| public  boolean delete()       | 删除文件、空文件夹，只能删除空文件夹，删除的文件不会进入回收站 |
| public String[] list()         | 获取当前目录下所有的"一级文件名称"到一个字符串数组中去返回。 |
| public File[] listFiles()      | 获取当前目录下所有的"一级文件对象"到一个文件对象数组中去返回 <br /> - 当主调是文件，或者路径不存在时，返回null<br /> - 当主调是空文件夹时，返回一个长度为0的数组<br /> - 当主调是一个有内容的文件夹时，将里面所有一级文件和文件夹的路径放在File数组中返回<br /> - 当主调是一个文件夹，且里面有隐藏文件时，将里面所有文件和文件夹的路径放在File数组中返回，包含隐藏文件<br />- 当主调是一个文件夹，但是没有权限访问该文件夹时，返回null<br /> |



### FileInputStream

| **构造器**                                  | **说明**                       |
| ------------------------------------------- | ------------------------------ |
| public **FileInputStream(File file)**       | 创建字节输入流管道与源文件接通 |
| public **FileInputStream(String pathname)** | 创建字节输入流管道与源文件接通 |
|                                             |                                |
|                                             |                                |
|                                             |                                |

| **方法名称**                                    | **说明**                                                     |
| ----------------------------------------------- | ------------------------------------------------------------ |
| public int **read()**                           | 每次读取一个字节返回，如果发现没有数据可读会返回-1.          |
| public int **read(byte[]  buffer)**             | 每次用一个字节数组去读取数据，返回字节数组读取了多少个字节，如果发现没有数据可读会返回-1. |
| public byte[] readAllBytes() throws IOException | 【JDK9引入，JDK11完善大文件校验】直接将当前字节输入流对应的文件对象的字节数据装到一个字节数组返回 |
|                                                 |                                                              |
|                                                 |                                                              |



### FileOutputStream

| **构造器**                                               | **说明**                                       |
| -------------------------------------------------------- | ---------------------------------------------- |
| public FileOutputStream(File file)                       | 创建字节输出流管道与源文件对象接通             |
| public FileOutputStream(String filepath)                 | 创建字节输出流管道与源文件路径接通             |
| public FileOutputStream(File file，boolean append)       | 创建字节输出流管道与源文件对象接通，可追加数据 |
| public FileOutputStream(String filepath，boolean append) | 创建字节输出流管道与源文件路径接通，可追加数据 |

| **方法名称**                                         | **说明**                     |
| ---------------------------------------------------- | ---------------------------- |
| public void write(int a)                             | 写一个字节出去               |
| public void write(byte[] buffer)                     | 写一个字节数组出去           |
| public void write(byte[] buffer , int pos , int len) | 写一个字节数组的一部分出去。 |
| public void close() throws IOException               | 关闭流。                     |





### FileReader

| **构造器**                             | **说明**                       |
| -------------------------------------- | ------------------------------ |
| public **FileReader(File file)**       | 创建字符输入流管道与源文件接通 |
| public **FileReader(String pathname)** | 创建字符输入流管道与源文件接通 |

| **方法名称**                        | **说明**                                                     |
| ----------------------------------- | ------------------------------------------------------------ |
| public int **read()**               | 每次读取一个字符返回，如果发现没有数据可读会返回-1.          |
| public int **read(char[]  buffer)** | 每次用一个字符数组去读取数据，返回字符数组读取了多少个字符，如果发现没有数据可读会返回-1. |



### FileWriter

| **构造器**                                         | **说明**                                       |
| -------------------------------------------------- | ---------------------------------------------- |
| public FileWriter(File file)                       | 创建字节输出流管道与源文件对象接通             |
| public FileWriter(String filepath)                 | 创建字节输出流管道与源文件路径接通             |
| public FileWriter(File file，boolean append)       | 创建字节输出流管道与源文件对象接通，可追加数据 |
| public FileWriter(String filepath，boolean append) | 创建字节输出流管道与源文件路径接通，可追加数据 |

| **方法名称**                               | **说明**                                             |
| ------------------------------------------ | ---------------------------------------------------- |
| void  write(int c)                         | 写一个字符                                           |
| void  write(String str)                    | 写一个字符串                                         |
| void  write(String str, int off, int len)  | 写一个字符串的一部分                                 |
| void  write(char[] cbuf)                   | 写入一个字符数组                                     |
| void  write(char[] cbuf, int off, int len) | 写入字符数组的一部分                                 |
| public  void flush() throws IOException    | 刷新流，就是将内存中缓存的数据立即写到文件中去生效！ |
| public  void close() throws IOException    | 关闭流的操作，包含了刷新！                           |

### BufferedInputStream

| **构造器**                                 | **说明**                                                     |
| ------------------------------------------ | ------------------------------------------------------------ |
| public BufferedInputStream(InputStream is) | 把低级的字节输入流包装成一个高级的缓冲字节输入流，从而提高读数据的性能 |

### BufferedOutputStream

| **构造器**                                   | **说明**                                                     |
| -------------------------------------------- | ------------------------------------------------------------ |
| public BufferedOutputStream(OutputStream os) | 把低级的字节输出流包装成一个高级的缓冲字节输出流，从而提高写数据的性能 |

### BufferedReader

| **构造器**                       | **说明**                                                     |
| -------------------------------- | ------------------------------------------------------------ |
| public  BufferedReader(Reader r) | 把低级的字符输入流包装成字符缓冲输入流管道，从而提高字符输入流读字符数据的性能 |

| **方法**                  | **说明**                                         |
| ------------------------- | ------------------------------------------------ |
| public  String readLine() | 读取一行数据返回，如果没有数据可读了，会返回null |

### BufferedWriter

| **构造器**                       | **说明**                                                     |
| -------------------------------- | ------------------------------------------------------------ |
| public  BufferedWriter(Writer r) | 把低级的字符输出流包装成一个高级的缓冲字符输出流管道，从而提高字符输出流写数据的性能 |

| **方法**               | **说明** |
| ---------------------- | -------- |
| public  void newLine() | 换行     |



## math

### BigDecimal

#### valueOf

#### add

#### substract

#### multiply

#### divide

#### compareTo



## text

### SimpleDateFormat

#### format

#### parse



## time

### Duration

#### between

#### getSeconds

#### getNano

#### toMillis

#### toMinutes

#### toHours

#### toDays





### Period

#### between

#### getYears

getMonths





### Instant

#### now

#### getEpochSecond

#### getNano

#### plusSeconds

#### minusSeconds

#### equals

#### isAfter

#### isBefore





### LocalDateTime

#### now

#### of

#### getYear

#### getMonthValue

#### getDayOfMonth

#### getHour

#### getMinute

#### getSecond

#### getNano

#### getDayOfYear

#### getDayOfWeek

#### withYear

#### withMonth

#### withDayOfMonth

#### withHour

#### withMinute

#### withSecond

#### withNano

#### plusYears

#### plusMonths

#### plusDays

#### plusHours

#### plusMinutes

#### plusMinutes

#### plusSeconds

#### plusNanos

#### minusYears

#### minusMonths

#### minusDays

#### minusHours

#### minusMinutes

#### minusSeconds

#### minusNanos

#### isAfter

#### isBefore

#### isEqual

#### toLocalDate

#### toLocalTime

#### parse





### LocalDate





### ZoneId

#### getAvailableZoneIds

#### systemDefault

#### 

### ZonedDateTime

#### now

#### getYear

#### getMonthValue

#### getDayOfMonth

#### getHour

#### getMinute

#### getSecond

#### getNano

#### withYear

#### withMonth

#### withDayOfMonth

#### withHour

#### withMinute

#### withSecond

#### withNano





### format

#### DateTimeFormatter

##### ofPattern

##### format





### DayOfWeek

#### getValue





# lombok

## @Data

## @AllArgsConstructor

## @NoArgsConstrustor
