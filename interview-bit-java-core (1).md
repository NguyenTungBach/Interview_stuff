# Java
## _Basic_

### 1. Tại sao Java là ngôn ngữ độc lập nền tảng?
- Trình biên dịch của java biên dịch code java thành bytecode - một cái độc lập nền tảng có thể chạy trên nhiều hệ thống.
- Điều kiện duy nhất để chạy cái bytecode là máy phải có JRE.

### 2. Tại sao Java không thuần hướng đối tượng?
- Vì java hỗ trợ các kiểu dữ liệu nguyên thủy, mấy cái này không phải object.

### 3. Tại sao trong java không có pointer như c/c++?
- Pointer khá phức tạp và không an toàn cho người mới lập trình. Java thì tập trung vào tính đơn giản nên việc sử dụng pointer sẽ khiến nó khá thách thức.
- Ngoài ra thì nếu dùng pointer người dùng có thể truy cập trực tiếp vào bộ nhớ -> tổn hại đến security.

### 4. Local variable và instance variable là gì?
- **Instance variable**: biến có thể truy cập bởi mọi method trong class, được khai báo trong class, ngoài method
- **Local variable**: được khai báo trong method, block hoặc constructor và chỉ được truy cập bên trong đấy.

### 5. Data encapsulation là gì?
- Là một concept của OOP nhằm che giấu các thuộc tính và hành vi trong 1 đơn vị.
- Đảm bảo các đối tượng độc lập với các đối tượng khác bởi nó có thuộc tính, hành vi, chức năng của riêng nó.

### 6. JIT là gì?

### 7. equals() và ==?
- equals() là method của class Object, == là operator (toán tử).
- equals() so sánh nội dung , == so sánh địa chỉ.

### 8. Vòng lặp vô tận trong java
- Dùng **for**:
```sh
for (;;){
    // Business logic
    // Any break logic
}
```
- Dùng **while**:
```sh
while (true){
    // Business logic
    // Any break logic
}
```
- Dùng **do**:
```sh
do{
    // Business logic
    // Any break logic
}while(true)
```

### 9. Constructor overloading là gì?
- Là tạo ra nhiều constructor trong class với tên giống nhau nhưng khác tham số.
- Dựa vào số lượng tham số cùng với kiểu dữ liệu tương ứng, compiler phân biệt các constructor

### 10. Override, overload
### 11. Giải thích 1 try block nhiều catch block trong java
- Có thể có nhiều catch nhưng chỉ thằng đầu tiên thỏa mãn điều kiện catch mới được executed

### 12. Từ khóa final
- Biến final: 
  - Không thể thay đổi giá trị khi đã được assigned.
  - Nếu biến final chưa được khởi tạo giá trị thì muốn khởi tạo nó chỉ có thể dùng constructor hoặc 1 Instance Initialization Block.
- Method final:
    - Không thể bị override
    - Constructor không thể là final
- Class final: không thể được kế thừa, nhưng có thể kế thừa class khác.

### 13. final, finally, finalize
- **final**: như trên. Nó là từ khóa
- **finally**: Khối lệnh finally trong java là một khối chứa các lệnh luôn được thực thi, ngay cả khi chương trình có bắt được lỗi hay không. Nó là một khối
- **finalize**:Finalize được sử dụng để thực hiện quá trình xử lý xóa ngay trước khi đối tượng thu gom rác (Garbage collector). Nó là một method.

### 14. super()
- Bất cứ khi nào bạn tạo ra instance (thể hiện) của lớp con, một instance của lớp cha được tạo ra ngầm định.
- Từ khóa super trong java là một biến tham chiếu được sử dụng để tham chiếu trực tiếp đến đối tượng của lớp cha gần nhất.
- Từ khóa super có 3 cách sử dụng sau:
    - Gọi trực tiếp hàm dựng (constructor) của lớp cha gần nhất.
    - Gọi trực tiếp thuộc tính (field) của lớp cha gần nhất.
    - Gọi trực tiếp phương thức (method) của lớp cha gần nhất.


### 16. Static method có override dc k?
Không thể override static method vì override là kĩ thuật dựa trên quá trình gán (binding) động khi ct đang chạy (runtime polymophism), static method được gán tĩnh trong compile time

### 15. Static method có overload dc k?
Có

### 17. Garbage collector để làm gì?
- Garbage là các object k được tham chiếu đến nữa
- Garbage collector sẽ truy tìm garbage để giải phóng bộ nhớ
- GC là tự động và có thể tùy chỉnh

### 18. Stack hay heap dc dọn dẹp bởi garbage collector
Heap

### 19. Tại sao String là immutable
- String Pool: Biết là string sẽ được sử dụng nhiều nên mấy anh dev java tối ưu hóa việc sử dụng string bằng String pool. String pool là một vùng nhớ nằm trong Heap để lưu trữ các object String.
Việc này sẽ làm giảm các String object tạm thời bằng cách "chia sẻ". Mutable thì không thể "chia sẻ" => string immutable để phục vụ cho cái String pool ?? :D ??
>>String value = “abc” -> abc là string literal
Khi khai báo string kiểu trên JVM sẽ truy cập vào String pool tìm xem có cái ô nhớ nào có giá trị như này k, nếu có thì string mới sẽ tham chiếu tới địa chỉ của ô nhớ đấy; không có thì tạo ô nhớ mới.
- Multithreading: Sự an toàn của các thread lquan đến string object là 1 vấn đề quan trọng trong java. String immutable không thay đổi rồi nên không cần phải lo đồng bộ hóa => sử dụng string ở các thread khác nhau 
- Collection: Trong  Hashtables and HashMaps key là string object. Nếu string có thể thay đổi thì sẽ tiềm ẩn nhiều nguy hiểm khi key có thể bị thay đổi

### 20. String, StringBuffer, StringBuilder
- Lưu trữ: String được lưu trữ trong StringPool, 2 cái kia trong Heap ngoài pool
- Mutable: String là immutable, 2 cái kia mutable
- Hiệu quả: String khá chậm, StringBuilder là nhanh nhất, StringBuffer chậm hơn 1 ít
- Thread safe: Thường k sử dụng String
    - Builder phù hợp với single thread do không synchronization tức là instance của nó k thể dc chia sẻ giữa các thread.
    - Buffer có method tương tự Builder nhưng thread safe, synchronization phù hợp với multi thread

### 21. Interface và abstract class
|| Abstract class | interface |
| ------ | ------ | ------ |
| method | có thể có non-abstract class | chỉ có abstract class |
| biến | có thể có non-static, non-final variable| chỉ có biến static final |
| kế thừa | không hỗ trợ đa kế thừa | hỗ trợ đa kế thừa |
| AM | có thể có private, protected | mặc định là public |

### 22. Trong java có thể override static, private method?
- **KHÔNG** 
- Static giống câu 16
- Private mà override được thì private làm gì?

### 23. HashSet vs TreeSet
- Cả 2 đều không đồng bộ và k cho phép duplicate
- Khác nhau

    || HashSet | TreeSet |
    | ------ | ------ | ------ |
    | method | có thể có non-abstract class | chỉ có abstract class |
    | biến | có thể có non-static, non-final variable| chỉ có biến static final |
    | kế thừa | không hỗ trợ đa kế thừa | hỗ trợ đa kế thừa |
    | AM | có thể có private, protected | mặc định là public |
    
### 25. JDK - JRE - JVM
- JDK là một gói các công cụ phát triển và thư viện hỗ trợ cung cấp môi trường để phát triển và thực thi ct Java.
- JDK = JRE (thực thi) + development tools (phát triển)
- JRE = JVM + một số file và thư viện mà JVM sử dụng
- JRE cung cấp môi trường để thực thi (không bao gồm phát triển) ct Java.
- JVM cung cấp môi trường runtime để java bytecode thực thi. Java “Write once, run anywhere” là nhờ JVM

### 30. Java work as "pass by value" hay "pass by reference"
- Java là pass by value, không có pass by reference trong java
- Khi truyền giá trị kiểu Primitive vào method thì nó sẽ là Pass-by-value thì không có gì bàn cãi.
- Khi truyền object vào method, pạn thấy object bên ngoài bị thay đổi nếu bên trong method thay đổi. Nghe rất pass by reference nhưng thực ra không phải: bản chất là khi object được pass thì reference của object được clone ra một cái mới và pass vào method. Khi đó thì có 2 reference trỏ vào object này. Và vì thế nên khi có thay đổi diễn ra trong method cũng làm thay đổi cái object -> Do đó đây là pass by value

### 39. Có thể gọi đến constructor bên trong constructor khác
- Có, dùng this()

### 40. Trong array thì cấp phát bộ nhớ là liền kề còn ArrayList thì không? Tại sao?

# _Advanced_

### 42. Tạo mới String bằng new khác literal như nào?
```sh
String first = "InterviewBit"
String second = "InterviewBit";
```
- Khi tạo mới 1 object string bằng cách trên thì JVM sẽ tìm trong String pool xem có String  "InterviewBit" chưa, nếu chư thì tạo mới, nếu có rồi thì không tạo thêm. Như hình thì ở câu lệnh thứ 2 sẽ không có string nào dc khởi tạo mà second sẽ trỏ đến địa chỉ củ  "InterviewBit" hay **first == second**
 ```sh
String first = new String("InterviewBit");
String second = new String("InterviewBit");
```
- Ngược lại, ở dòng đầu tiên, 2 object được tạo ra: 1 trong pool và 1 trong heap; ở dòng 2 sẽ có thêm 1 object được tạo ra trong heap và **first != second** do 2 thằng trỏ vào 2 object khác nhau trong heap

### 43. Dù đã có Garbage Collectoer (GC) tuy nhiên vẫn có thể xảy ra tràn bộ nhớ?
- GC hỗ trợ việc tìm kiếm và loại bỏ các object không cần đến nữa trong chương trình.
- Tuy nhiên trong 1 chương trình, nếu 1 object không thể dc truy cập đến thì GC vô dụng với nó. Tới 1 giới hạn thì sẽ thiếu bộ nhớ để khởi tạo object -> tràn
- Hơn thế nữa, việc cạn kiệt bộ nhớ heap xảy ra khi các object dc tạo ra bằng những cách mà nó sẽ vẫn remain và tiêu hao bộ nhớ (dù đã k còn dc dùng đến?)

### 44. Tại sao cần đồng bộ hóa?
- Các quy trình khác nhau có thể được xử lý đồng thời là nhờ đồng bộ.
- Một số trường hợp các thread cần chia sẻ 1 nguồn tài nguyên cụ thể nào đó

### 45. Dấu ... trong đoạn code sau là gì?
 ```sh
public void fooBarMethod(String... variables){
// method code
}
```
- ... được gọi là Variable Argument (varargs) a.k.a đối số linh động cho phép phương thức chấp nhận các đối số zero hoặc muliple
- Chỉ có thể chỉ định **một** đối số varargs cho phương thức.
- Đối số varargs phải ở vị trí **cuối cùng**.
- Không nên overload method dùng varargs do trong 1 số trường hợp chương trình sẽ ambigous
```sh
void method(String... a, int... b) {} //Compile time error
void method(int... a, String b) {}    //Compile time error
```
### 46. Java thread life cycle
- New: Khi một instance được khởi tạo nhưng chưa được start();
- Active: Khi một thread được start()
    - Runnable: trước khi run() được JVM gọi dến
    - Running: khi run() được gọi
- Non-runnable (Blocked/Waiting):
    - Blocked: 1 Thread đang chờ 1 thread khác thoát cái " khối đồng bộ" trước khi có thể chạy.
    - Waiting: 1 thread đang chờ tín hiệu từ 1 thread khác để có thể chạy
- Terminated: khi run() đã hoàn thành hoặc thread chết do lỗi?

### 47. Mảng đã sắp xếp so với chưa sx
- Sắp xếp rồi dễ search hơn: độ phức tạp là O(log n) so với O(n).
- Sắp xếp rồi thêm phần tử mới lâu hơn: O(n) do cần phải sắp xếp lại so với O(1).

### 48. Có thể import 1 class hoặc package nhiều hơn 1 lần k? Điều gì sẽ xảy ra trong runtime
- Có
- Điều này là dư thừa vì JVM chỉ load những class hoặc package này 1 lần.

### 49. Trong th package có package con thì chỉ import cha có import con k?
- **KHÔNG**
- Phải import package con tường minh

### 50. finally block có chạy k nếu có System.exit(0) ở cuối try block
- **KHÔNG**
- Chương trình sẽ terminate ngay và finally sẽ k chạy.

### 53. Tại sao lại nói length() của String k trả về kq chuẩn xác?
- TL;DR: hàm này đến số code unit, và có 1 số kí tự được encode bằng 2 code unit dẫn tới đếm thành 2 kí tự -> sai lệch
- Giải pháp là đếm số code point chứ k đếm code unit
     ```sh
            String str = "\uD835\uDD38"; 
            System.out.println(str);//prints 𝔸
            System.out.println(str.length()); //prints 2
            System.out.println(str.codePointCount(0, str.length()));// prints 1
    ```

### 54. Code dưới kết quả như lào?
```sh
        public class InterviewBit{
            public static void main(String[] args){
                System.out.println('b' + 'i' + 't');
            }
        }
```
- Kí tự đặt trong "" a.k.a string literal thì mới in ra **bit**
- Kí tự đặt trong '' a.k.a character literal sẽ cộng giá trị ascii tương ứng và in ra 319.
     ```sh
        ‘b’ = 98
        ‘i’ = 105
        ‘t’ = 116
        98 + 105 + 116 = 319
    ```

### 55. Có những cách nào để object đủ đk cho GC dọn
- Cách 1: set reference của object thành null sau khi nó đã hoàn thành nhiệm vụ
    ```sh
        public class IBGarbageCollect {
            public static void main (String [] args){
                String s1 = "Some String";
                // s1 referencing String object - not yet eligible for GC
                s1 = null; // now s1 is eligible for GC
            }
        }
    ```
- Cách 2: Trỏ cái reference sang object khác
  ```sh
        public class IBGarbageCollect {
            public static void main (String [] args){
                String s1 = "To Garbage Collect";
                String s2 = "Another Object";
                System.out.println(s1); // s1 is not yet eligible for GC
                s1 = s2; // Point s1 to other object pointed by s2
                /* Here, the string object having the content "To Garbage Collect" is not referred
            }
        }
    ``` 
- Cách 3:Island of Isolation (Đảo cô lập ??:D??) 2 biến reference trỏ vào 2 instance của cùng 1 class; 2 biến này trỏ vào nhau; 2 object được 2 biến này trỏ vào giờ sẽ chả có reference nữa -> tạo thành đảo cô lập?
     ```sh
        public class IBGarbageCollect {
            public static void main (String [] args){
                IBGarbageCollect ibgc1 = new IBGarbageCollect();
                IBGarbageCollect ibgc2 = new IBGarbageCollect();
                ibgc1.ib = ibgc2; //ibgc1 points to ibgc2
                ibgc2.ib = ibgc1; //ibgc2 points to ibgc1
                ibgc1 = null;
                ibgc2 = null;
                /*
                * We see that ibgc1 and ibgc2 objects refer
                * to only each other and have no valid
                * references- these 2 objects for island of isolcation - eligible for GC
                */
            }
        }
    ```
    
### 56-60. Algorithm