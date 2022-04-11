# **Typescript cơ bản**

## **Typescript là gì?**

- Là ngôn ngữ mã nguồn mở của Microsoft
- Được build dựa trên ngôn ngữ Javascript
- Là phiên bản nâng cao của Javascript bởi vì có thêm type và lớp hướng đối tượng mà Javascript không có.

> Nguồn: [Typescript github](https://github.com/microsoft/TypeScript)

---

## **Javascript và Typescript cái nào tốt hơn?**

### **Javascript:**

- Linh hoạt
- Không cần phải khai báo kiểu dữ liệu và cũng không cần tìm hiểu kiểu dữ liệu khi sử dụng libs
- Code nhanh khi làm việc 1 mình
- Cần phải hiểu rõ javascript để tránh được những lỗi vặt

### **Typescript:**

- Gặp khó khăn với type system vì thường xuyên bị lỗi liên quan tới kiểu dữ liệu khi bạn chưa quen.
- Bù lại được nhắc code bao ngon luôn.
- Đỡ bị lỗi vặt hơn
- Code 1 mình thì hơi chậm ban đầu vì phải khai báo kiểu dữ liệu đầy đủ
- Code trong 1 team thì khá lợi vì auto complete.

---

## **Cài đặt typescript**

```shell
# Sử dụng yarn
yarn global add typescript ts-node ts-lib @types/node
```

---

## **Tìm hiểu Typescript**

### **Làm sao để chuyển file ts sang file js.**

```shell

tsc file_name.ts
node file_name.js
```

**Note:** Sau khi chạy lệnh trên thì typescript sẽ chuyển đổi file ts sang file js tương ứng. Sau đó mình sẽ chạy lệnh `node file_name.js` để thực thi như bình thường. Chúng ta không thể chạy trực tiếp file ts vì hệ thống không hiểu được. Chúng ta phải chuyển file ts sang js thì hệ thống mới hiểu và biên dịch được.

### **Có cách nào để chạy trực tiếp file ts không?**

```shell

ts-node file_name.ts
```

**Note:** ts-node cho phép nhận vào file typescript và thực hiện thực thi biên dịch file mà không cần chuyển đổi sang js.

---

### **Static type checking**

- Typescript giúp phát hiện ra lỗi ngay khi code
- Giúp tránh lỗi typo
- Tiết kiệm thời gian debug

### **Explicit type (Khai báo tường minh)**

- Khai báo kiểu dữ liệu trong typescript thì sử dụng dấu hai chấm sau tên biến.

```shell

let count: number = 4;
let isActive: boolean = true;
const numberList: number[] = [1,2,3];
```

### **Infered type**

- Typescript đủ thông minh để tự detect ra biến đang dùng là thuộc kiểu dữ liệu gì khi mình không khai báo cụ thể

```shell

# Tự động hiểu count là kiểu number
let count = 4;
```

### **Các kiểu dữ liệu thường gặp**

- Kiểu nguyên thủy: number, boolean, string, null, undefined, symbol
- Kiểu tham chiếu: array, object, function
- Ngoài ra còn có thêm any, unknown, void, never,...

Created by Suu Pham SP
