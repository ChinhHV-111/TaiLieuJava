
# Tìm Hiểu Về Ngôn Ngữ Java

## 1. Ngôn ngữ Java là gì?
Java là một ngôn ngữ lập trình đa nền tảng, hướng đối tượng và có tính bảo mật cao. Được phát triển bởi Sun Microsystems vào năm 1995 và hiện nay thuộc sở hữu của Oracle. Java nổi bật nhờ khả năng chạy trên nhiều hệ điều hành khác nhau mà không cần thay đổi mã nguồn.

## 2. Lý do ra đời của Java
Java được tạo ra với mục tiêu giúp lập trình viên viết một lần và có thể chạy ở bất kỳ đâu ("Write Once, Run Anywhere" - WORA). Java giải quyết vấn đề tương thích đa nền tảng mà nhiều ngôn ngữ khác không làm được vào thời điểm đó. Ngoài ra, Java còn được thiết kế để trở nên đơn giản, mạnh mẽ và an toàn.

## 3. Cách Java hoạt động, điều gì xảy ra khi chạy code Java (.java)?
1. **Biên dịch mã nguồn (.java)**: Khi bạn viết mã Java, nó sẽ được lưu với đuôi `.java`. Sau đó, mã này sẽ được biên dịch thành mã bytecode bằng trình biên dịch của Java (javac). Bytecode được lưu trong file `.class`.
2. **Chạy chương trình (.class)**: Bytecode không phải là mã máy, vì vậy nó không thể chạy trực tiếp trên phần cứng. Thay vào đó, nó được thực thi bởi Java Virtual Machine (JVM), một môi trường giả lập đa nền tảng.

Quá trình này giúp Java trở nên đa nền tảng, vì chỉ cần có JVM trên bất kỳ hệ điều hành nào, chương trình Java có thể chạy trên đó mà không cần thay đổi mã nguồn.

## 4. Cấu trúc một chương trình Java

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); // In ra màn hình dòng chữ Hello, World!
    }
}
```
- `public class HelloWorld`: Khai báo một lớp (class) với tên `HelloWorld`.
- `public static void main(String[] args)`: Đây là phương thức khởi động (entry point) của chương trình.
- `System.out.println()`: In nội dung ra màn hình.

## 5. Package là gì?
Package trong Java là một cơ chế để tổ chức các lớp liên quan lại với nhau thành nhóm. Nó giúp tránh xung đột tên lớp và giúp mã nguồn được tổ chức dễ quản lý hơn. Ví dụ:

```java
package com.example.myapp;
```

Trong ví dụ trên, lớp thuộc về package `com.example.myapp`.

## 6. Syntax cơ bản
### a. Khai báo biến nguyên thủy
Java hỗ trợ các kiểu dữ liệu nguyên thủy như: `int`, `float`, `double`, `char`, `boolean`. Ví dụ:

```java
int age = 25;
float height = 1.75f;
char grade = 'A';
boolean isStudent = true;
```

### b. Làm quen với vòng lặp
Java hỗ trợ các vòng lặp như: `for`, `while`, và `do-while`.

- Vòng lặp `for`:
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

- Vòng lặp `while`:
```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

### c. Câu lệnh rẽ nhánh
Câu lệnh `if`, `else if`, `else` giúp kiểm tra điều kiện.

```java
int number = 10;
if (number > 0) {
    System.out.println("Số dương");
} else if (number < 0) {
    System.out.println("Số âm");
} else {
    System.out.println("Số không");
}
```

### d. Mảng trong Java
Mảng (Array) trong Java là một cấu trúc dữ liệu dùng để lưu trữ nhiều giá trị có cùng kiểu dữ liệu.

```java
int[] numbers = {1, 2, 3, 4, 5};
for (int number : numbers) {
    System.out.println(number);
}
```

## 7. Tổng quan về Class và Object

### a. Từ khóa `this`
Từ khóa `this` được sử dụng để tham chiếu đến đối tượng hiện tại của lớp.

```java
public class Person {
    private String name;

    public Person(String name) {
        this.name = name; // Sử dụng this để phân biệt biến instance và tham số phương thức
    }
}
```

### b. Constructor
Constructor là một phương thức đặc biệt được gọi khi một đối tượng mới của lớp được tạo ra.

```java
public class Person {
    public Person() {
        System.out.println("Constructor được gọi");
    }
}
```

### c. Access Modifier
Access Modifier quy định phạm vi truy cập của các thành viên trong lớp. Các modifier phổ biến:
- `public`: Truy cập từ bất kỳ đâu.
- `private`: Chỉ truy cập trong lớp.
- `protected`: Truy cập trong cùng package hoặc các lớp con.
- `default`: Chỉ truy cập trong cùng package.

### d. Getter và Setter
Phương thức getter và setter được sử dụng để truy cập và cập nhật các biến private trong lớp.

```java
public class Person {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

### e. Từ khóa `static`
Từ khóa `static` được sử dụng để khai báo các thành viên chung cho tất cả các đối tượng của lớp, thay vì mỗi đối tượng có một bản sao riêng.

```java
public class MathUtils {
    public static final double PI = 3.14159;

    public static double sum(double a, double b) {
        return a + b;
    }
}
```
