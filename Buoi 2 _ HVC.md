# 1. Object là gì?
Trong Java, **Object** là một thực thể của một lớp (class), đại diện cho các thực thể thực tế trong thế giới thật. Nó chứa các thuộc tính (attributes) và hành vi (methods) của lớp đó. Object được sử dụng để truy cập vào các thuộc tính và phương thức của lớp.

# 2. Object được lưu thế nào trong Java?
Trong Java, Object được lưu trữ trong **Heap Memory**. Khi một Object được tạo ra bằng từ khóa `new`, Java sẽ cấp phát bộ nhớ cho Object đó trong Heap. Bộ nhớ được quản lý bởi **Garbage Collector** của Java, giúp giải phóng bộ nhớ của các Object không còn được tham chiếu.

# 3. Wrapper class
- **Wrapper Class** là các class được tạo ra để bao bọc các kiểu dữ liệu nguyên thuỷ.

|Biến nguyên thủy   | Wrapper Class  |
|---|---|
| byte  | Byte  |
| short  | Short  |
| int  | Integer  |
| long  | Long  |
| float  | Float  |
| double  | Double  |
| boolean  | Boolean  |
| char  | Character  |
- **Wrapper class** cung cấp các phương thức để thao tác với các kiểu dữ liệu nguyên thuỷ. Ví dụ: 
> Integer.parseInt()
>  Integer.toString() 
> Integer.valueOf()
> …
> 
# 4. Auto boxing / Auto unboxing
- **Auto Boxing** là quá trình chuyển đổi từ kiểu dữ liệu nguyên thuỷ sang kiểu dữ liệu dạng **Wrapper Class**.
```java
int a = 1;
Integer x = a;
```
- **Auto UnBoxing** là quá trình chuyển đổi từ dữ liệu dạng **Wrapper Class** sang kiểu dữ liệu nguyên thuỷ.
```java
Integer x = 1;
int a = x;
```
- **Lưu ý**: Khi sử dụng Auto boxing và Auto unboxing phải kiểm tra giá trị null trước khi sử dụng.
```java
Integer a = null;
```
# 5. String và StringBuilder trong Java
## 5.1 String
- **String** là một class trong Java, nó được sử dụng để lưu trữ một chuỗi các ký tự. Một đối tượng **String** được tạo ra bằng cách sử dụng từ khóa new và có thể được khởi tạo bằng một chuỗi ký tự hoặc một đối tượng **String** khác.
```java
String str = "ProPTIT";
String demoStr = new String (“LapTrinhTuTraiTim”);
```
- Để nhập vào **String** từ bàn phím, ta sử dụng hàm **nextLine()** của Scanner
```java
Scanner sc = new Scanner(System.in);
String str = sc.nextLine();
```

## 5.2 StringBuilder
- **StringBuilder** là một class trong Java, nó được sử dụng để lưu trữ một chuỗi các ký tự. Một đối tượng **StringBuilder** được tạo ra bằng cách sử dụng từ khóa new và có thể được khởi tạo bằng một chuỗi ký tự hoặc một đối tượng String khác.
```java
StringBuilder demoStr = new StringBuilder ("ProPTIT");
```
- Để nhập vào **StringBuilder** từ bàn phím, ta sử dụng hàm **nextLine()** của Scanner
```java
Scanner sc = new Scanner(System.in);
StringBuilder str = sc.nextLine();
```

# 6. Về equals và hashcode, toán tử ==
- **equals()**: là phương thức dùng để so sánh giá trị của hai đối tượng. Nó cần được override trong các lớp nếu muốn so sánh theo giá trị.
- **==**: toán tử này dùng để so sánh địa chỉ vùng nhớ của hai đối tượng. Nó chỉ trả về `true` khi hai đối tượng tham chiếu đến cùng một địa chỉ.
- **hashCode()**: là phương thức trả về mã băm của đối tượng, thường dùng trong các cấu trúc dữ liệu như `HashMap`.

# 7. Cách Java truyền tham số, pass by value
Java truyền tham số bằng **pass by value**. Điều này có nghĩa là khi một biến được truyền vào phương thức, Java sẽ truyền một bản sao của giá trị của biến đó, không phải là biến gốc. Tuy nhiên, trong trường hợp là một Object, Java truyền bản sao của tham chiếu (reference), nên các thay đổi trên Object sẽ ảnh hưởng đến bản gốc.

# 8. Tại sao pass by value mà String lại thay đổi được?
String trong Java là bất biến (immutable), khi thay đổi giá trị của một String, Java sẽ tạo ra một đối tượng String mới thay vì thay đổi trực tiếp trên đối tượng ban đầu.

# 9. Các khái niệm cơ bản về Garbage Collector
**Garbage Collector (GC)** là cơ chế trong Java quản lý bộ nhớ tự động, giúp thu hồi bộ nhớ của các đối tượng không còn được tham chiếu. GC làm việc trong nền và giải phóng bộ nhớ trong Heap, giúp giảm rò rỉ bộ nhớ và tăng hiệu suất của ứng dụng.

- **Young Generation**: Nơi các Object mới được tạo.
- **Old Generation**: Nơi các Object sống lâu chuyển vào.
- **Permanent Generation**: Nơi lưu trữ metadata của các class.

## 10. Các thuật toán GC phổ biến:
- **Serial GC**: Thu gom bộ nhớ theo cách đơn luồng, phù hợp cho các ứng dụng nhỏ.
- **Parallel GC**: Sử dụng nhiều luồng để thu gom bộ nhớ, giúp tăng hiệu suất cho các ứng dụng lớn.
- **G1 GC (Garbage-First)**: Được thiết kế để xử lý các heap lớn, giảm thiểu thời gian dừng của ứng dụng.

