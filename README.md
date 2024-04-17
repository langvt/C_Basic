
<div>
    <div>
        <details>
        <summary><h1>Kiểu dữ liệu</h1></summary>

  ![kieu du lieu](./Pic/Kieu_Dulieu(1).PNG)
  ![kieu du lieu](./Pic/Kieu_Dulieu(2).PNG)
- Để tính kích thước của một kiểu dữ liệu trong C,  dụng toán tử sizeof.
 ```C 
#include <stdio.h>

int main() {
    int x;
    int size_of_x = sizeof(x);

    printf("Kich thuoc cua bien x la: %d byte\n", size_of_x);

    return 0;
}
 ```
</details>


<div>
    <details>
        <summary><h1>Hàm</h1></summary>

 <div>
        <details>
        <summary><h2>Hàm có giá trị trả về</h2></summary>


- Sử dụng hàm có giá trị trả về khi bạn muốn hàm thực hiện một công việc cụ thể và trả về một kết quả cho phần gọi hàm. 
    - ví dụ :
```C
#include <stdio.h>

int add(int a, int b) {
    return a + b;
}
int main() {
    int x = 5;
    int y = 7;
    int sum = add(x, y);
    printf("Tong cua %d va %d la: %d\n", x, y, sum);
    return 0;
}
```
</details>
                
<details>
  <summary><h2>Hàm void</h2></summary>


- Sử dụng hàm void khi bạn muốn hàm thực hiện một tác vụ nhưng không cần trả về giá trị nào
    - ví dụ :
```C
#include <stdio.h>

void printHello() {
    printf("Hello World!\n");
}

int main() {
    printHello();
    return 0;
}
```
</details>
</details>

<div>
<details>
  <summary><h1>Lệnh điều kiện trong C</h1></summary> 
  <div>
    <details>
    <summary><h2>Câu lệnh If</h2></summary>

- Nếu điều kiện được thỏa mãn thì sẽ thực thi đoạn code bên trong nó.
  `if (điều kiện){
    Khối lệnh sẽ được thực hiện nếu <điều kiện> đúng.
}`

<details>
<summary>Ví dụ:</summary>

```C
#include <stdio.h>
int main(){
   int a;
   printf(“Nhap a = “); scanf(“%d”, &a);
 
   if (a % 2 == 0) // a chia hết cho 2
   {
       printf(“%d la so chan”, a);
   }
   printf(“\nXong!”);
} 
```
 - Câu lệnh If else
 ```C
 if (condition)
 {
   // statement1
   // khối lệnh sẽ thực hiện nếu điều kiện đúng
}else
{
   // statement2
   // khối lệnh sẽ thực hiện nếu điều kiện sai
}
```
- Ví dụ

```C
#include <stdio.h>
 
int main(){
   int a;
   printf(“Nhap a = “); scanf(“%d”, &a);
   if (a % 2 == 0) // a chia hết cho 2
   {
       printf(“%d la so chan”, a);
   }else{
       printf(« %d la so le », a) ;
   }
} 
```

 - Câu lệnh if … else if … else:

```C
	if (test expression1) 
	{
	// statement(1)
	}
	else if(test expression2) 
	{
	// statement(2)
	}
	else if (test expression3) 
	{
	// statement(3)
	}
	…
	else 
	{
	// statement(n)
	}
```
</details>
</details>

<details>
<summary><h2>Switch case</h2></summary>
- Lệnh switch case là một cấu trúc điều khiển & rẽ nhánh hoàn toàn có thể được thay thế bằng cấu trúc if else. Tuy nhiên, việc sử dụng switch case sẽ giúp code của chúng ta dễ viết và dễ đọc hơn.

```C
switch (expression)// tham số đầu vào 
​{
   case constant1:// điều kiện
     // statements(khối lệnh)
     break;
   case constant2:
     // statements
     break;
   default:
     // default statements
}
```
 - Case default sẽ được thực hiện nếu không có case nào khớp giá trị  

 <details>
<summary>Ví dụ</summary>

```C
#include <stdio.h>

int main(void) {
int thang =1 ;
switch ( thang){
case 1:
	printf("30 ngay\n");
	break;
case 12:
	printf("28 ngay\n");
	break;
	default:
	printf("khong hop le\n");
	}
return 0;
}
	//Tổng bằng 8
```
 - Nếu không break ở cuối mỗi case thì chương trình sẽ chạy tiếp xuống các case ngay bên dưới dẫn đến chương trình có thể sai ý đồ.
 - Nhưng cố ý không break,có thể hiển thị nhiều điện kiện với 1 nội dung

```C
int main(void) {
day = Mon; 
switch (day) {
case Mon:
case Tue:
case Wed:
case Thu:
case Fri:
 	printf("Ngày trong tuần\n");
 break;
case Sat:
case Sun:
 	printf("Ngày lễ\n");
 break;
default:
 	printf("Không tồn tại\n");
}
return 0;
}
```
</details>
</details>

**_if và switch :_**

 - if dùng để kiểm tra các điều kiện là toán tử so sánh (<, >, ==, !=, vv.) hoặc các toán tử logic (&&, ||, vv.).
 - switch dùng để so sánh một biểu thức với các giá trị khác nhau. Nó sẽ kiểm tra giá trị và thực hiện các hành động tương ứng với giá trị đó.
 - Switch sẽ so sánh các tính năng khác nhau,mã sạch sẽ hơn và dễ đọc.
 - Nên sử dụng switch case trong bài toán mul-ti choice, biểu thức điều kiện tính toán phức tạp nhưng phải có giá trị nguyên.

</details>

<details>
  <summary><h1>Vòng lặp</h1></summary>

  <details>
  <summary><h2>Vòng lặp for</h2></summary>

- Cú pháp:
```C
for ( giá trị ban đầu; điều kiện lặp; thuật toán   )
{
   // các lệnh cần lặp
}
```

 <details>
<summary>Ví dụ</summary>

```C
for (int i =0; i<100; i=i+2 )
{
   printf("test:%d\n",i);
   if(i==50){
	break;// i chạy tới 50 sẽ thoát ra khỏi vòng for
   }
}
```
```C
for (int i =0; i<100; i=i+2 )
{
   
   if(i==50){
	continue;// khi i tới 50 , sẽ bỏ qua 50 , chạy tới giá trị i=52
   }
   printf("test:%d\n",i);
}
```
- Vòng lặp for vô hạn:

```C
int i=0;
for (;; )
{
   i++;
   printf("test:%d\n",i);
   if(i==50){
	beak;// nếu không có break thì vòng lặp chạy vô hạn
   }
   
}
```
  </details>
    </details>

<details>
  <summary><h2>Vòng lặp while</h2></summary>

- Cú pháp:
```C
while ( điều kiện lặp đúng )
{
   // các lệnh cần lặp
}
```
- Ví dụ:
```C
int i =0;
while ( i <10 )
{
   printf("test:%d\n",i);
   i++;   
}
```
- While được sử dụng khi

  </details>
  
  <details>
  <summary><h2>Vòng lặp do while</h2></summary>

- Cú pháp:
```C
do{
	// các lệnh cần lặp
}
while ( điều kiện lặp đúng );
 
```
 
- do-while :Lệnh làm trước sau đó mới so sánh điều kiện 
  </details>
</details>




<details>
  <summary><h1>Struct và Union</h1></summary>

  **Struct và Union là 2 cấu trúc dữ liệu do lập trình viên định nghĩa bao gồm các biến với kiểu dữ liệu khác nhau.Tuy nhiên, về mặt lưu trữ trong bộ nhớ, chúng có sự khác biệt rõ rệt như sau:**

  <details>
  <summary><h2>Struct</h2></summary>

    Dữ liệu của các thành viên của struct được lưu trữ ở những vùng nhớ khác nhau. Do đó kích thước của 1 struct tối thiểu bằng kích thước các thành viên cộng lại tại vì còn phụ thuộc vào bộ nhớ đệm (struct padding).
- Ví dụ:
  ```C 
  #include <stdio.h>
  #include <conio.h>
  struct date
	{
		int d;
		int m;
		long y;
	};
  void main()
	{
		date dat = {4, 4, 2016};
		printf("\nSize of struct: %d", sizeof(date));//size 12
	
		printf("\ndate = %d", dat.d);//date=4
		printf("\nmonth = %d", dat.m);//month =4
		printf("\nyear = %d", dat.y);//year=2016
	
		getch();
	
	} 
	```

**Tại cùng 1 thời điểm run-time, có thể truy cập vào tất cả các thành phần của struct**
**Struct padding :** Chèn thêm các vùng nhớ trống giữa các member để đảm bảo việc dữ liệu trong struct được natually aligned(các thao tác đọc ghi trong bộ nhớ nhanh hơn )
> Ví dụ:

![Struct_Padding](./Struct_Padding.PNG)

![Struct_Padding](./Struct_Padding(2).PNG)

- Như vậy đối với struct B kích thước của nó sẽ là 16 bytes, trong đó có 14 bytes được sử dụng và 2 bytes bị padding. Chúng ta thấy rằng việc sắp xếp thứ tự các phần tử của struct có thể giúp cho việc xử dụng tài nguyên RAM trở lên hiệu quả hơn, tránh bị tốn quá nhiều bytes cho quá trình padding.

	**Sử dụng Struct khi bạn muốn lưu trữ nhiều thông tin có liên quan với nhau:**

	- Ví dụ: Một hồ sơ người dùng có tên, tuổi, địa chỉ, v.v.

	**Khi bạn muốn lưu trữ dữ liệu với các loại dữ liệu khác nhau:**
	- Ví dụ: Một khối dữ liệu đại diện cho một ngày gồm ngày, tháng, năm là các kiểu dữ liệu khác nhau.

	**Khi bạn muốn có một cấu trúc dữ liệu linh hoạt, mà mỗi thành phần có thể được truy cập một cách dễ dàng:**
	- Ví dụ: Các thành phần của một hình học như điểm, đường, v.v.
  </details>

 <details>
  <summary><h2>Union</h2></summary>

  **Union : Dữ liệu các thành viên sẽ dùng chung 1 vùng nhớ. Kích thước của union được tính là size lớn nhất của kiểu dữ liệu trong union.**

  - cho phép lưu trữ các biến khác nhau trong cùng một vị trí bộ nhớ. Khi một giá trị mới được gán cho union, giá trị trước đó được ghi đè. Điều này có nghĩa là union chỉ lưu trữ một giá trị duy nhất tại một thời điểm.
	 
	- ví dụ 1:
	```C
	#include <stdio.h>
	#include <conio.h>
 
	union date
	{
		int d;
		int m;
		int y;
	};
 
	void main()
	{
		date dat;
	
		printf("\nSize of union: %d", sizeof(date));//4
		dat.d = 24;
		dat.m = 9;
		dat.y = 2014;
	
		printf("\ndate = %d", dat.d);//2014
		printf("\nmonth = %d", dat.m);//2014
		printf("\nyear = %d", dat.y);/2014
	
		getch();
	}
	```
 - Vùng nhớ dành cho union date là 4 byte. Vùng nhớ này sẽ chứa giá trị 24 khi dat.d = 24 được thực hiện. Tiếp đó, 9 sẽ được copy đè vào vùng nhớ này khi dat.m = 9 được thực hiện. Cuối cùng, 2014 được copy đè vào vùng nhớ khi dat.y = 2014 được thực hiện.
 **Tại cùng 1 thời điểm run-time, chỉ có thể truy cập 1 thành phần của union**

- ví dụ 2:

  ```C
  #include <stdio.h>
  #include <conio.h>
  union date
  {
    int d;
    int m;
    int y;
  };
 
  void main()
  {
		date dat;
	
		printf("\nSize of union: %d", sizeof(date));//4
		
		dat.d = 24;
		printf("\ndate = %d", dat.d);//24
	
		dat.m = 9;
		printf("\nmonth = %d", dat.m);//9
	
		dat.y = 2014;
		printf("\nyear = %d", dat.y);//2014
	
		getch();
  }
  ```
- Khác với VD1 ,các giá trị được gọi lần lượt , cứ mỗi lần kết thúc giá trị sẽ có 1 giá trị mới được ghi đè vào

**Sử dụng Union khi bạn muốn tiết kiệm bộ nhớ và chỉ lưu trữ một giá trị tại một thời điểm:**
- Khi bạn gán một thành viên, các giá trị của các thành viên khác sẽ thay đổi.
  </details>
</details>


<details>
  <summary><h1>Mảng (Array)</h1></summary>

<details>
  <summary><h2>Mảng</h2></summary>

  - Mảng (array) là các phần tử có kiểu dữ liệu đồng nhất. Các phần tử của mảng được lưu trong các vùng nhớ liên tiếp
- Một mảng thực sự là một con trỏ hằng (constant pointer) trỏ tới địa chỉ của phần tử đầu tiên trong mảng.
- Khai báo:
```- Kiểu dữ liệu tên mảng[]={};```
- Ví dụ :

 ```C
	 uint8_t mang[]={1,2,3,4,5};// kieu du lieu 8 bit >> 1 byte ,2 phan tu cach nhau 1 byte, mảng là 1 dãy địa chỉ 

	int main() {
		uint8_t *ptr=mang;// địa chỉ ô nhớ đầu tiên
		printf("gia tri:%d\n",*ptr);// in ra =1
		uint8_t *ptr=mang +1;
		printf("gia tri:%d\n",*ptr);// in ra =2
		
	
		 for(int i=0;i<5;i++){
			printf("Dia chi cua mang[%d]=%p, gia tri:%d",i,&mang[i],*i);
		 }
		// Thông qua con trỏ để biểu diễn mảng
		 for(int i=0;i<5;i++){
			printf("Dia chi cua mang[%d]=%p, gia tri:%d",i,ptr+i,*(ptr+i);
		 }
		return 0;
	}
```

  </details>

  <details>
  <summary><h2>Chuỗi</h2></summary>
  - Chuỗi là một tập hợp các ký tự (char) được lưu trữ trên các ô nhớ liên tiếp và luôn luôn có 1 ký tự null là \0 báo hiệu kết thúc chuỗi.
- Chú ý : Khi khai báo không để số trong[] , hãy để compiler tự làm

```C
char c[5] = "abcde"; // sai
```

- ví dụ:
 ```C
 	char arr[]="hello word"; 
	void doc_mang(char text[]){
		text[0]='a';
		text[1]='b';
	}
// vì chuỗi là 1 dãy địa chỉ , nếu ta làm như trên, nó sẽ thay đôi 
	

	int main() {
		doc_mang(arr);
		 for(int i=0;i<16;i++){
			printf("ky tu :%c, ma hex :0x%x, ",arr[i],arr[i] );
		 }

	// in ra la "abllo word"
		 
		return 0;
	}
```
  </details>

  </details>