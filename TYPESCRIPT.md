Static type-checking

Typescript có cơ chế tự check lỗi lúc runtime. Điều này giúp chúng ta có thể phát hiện lỗi trước khi code chạy.

Ví dụ dưới đây, Javascript sẽ không văng lỗi ngay lập tức nhưng Typescript sẽ phát hiện lỗi ngay.

![Static type-checking](./assets/static-type-checking.png)

Trường hợp này, Javascript sẽ trả về undefined, Typescript sẽ báo lỗi không tồn tại thuộc tính location.

![Static type-checking2](./assets/static-type2.png)

Types for Tooling

Typescript sẽ nhắc code cho bạn, nhắc những thuộc tính hay function có thể truy cập của 1 biến theo kiểu.

TypeScript compiler

```shell
#Chuyển file ts sang file js sử dụng tsc (tự động generate ra file js và thực thi câu lệnh của file đó)
tsc file_name.ts
node file_name.js
```

**Ghi chú:** Typescript sẽ phát hiện tất cả các lỗi typo, truyền thiếu params,...

Explicit Types (Kiểu tường minh)

Add thêm type cho person và date
![Annotation](./assets/annotation.png)

Nhiều khi chúng ta không cần phải khai báo tường minh kiểu dữ liệu cho 1 biến, mà Typescript đủ thông minh để detect ra được biến đó kiểu gì

![Infer](./assets/infer.png)

Any type

Khi bạn không biết được cụ thể kiểu dữ liệu của 1 biến thì có thể cân nhắc dùng any
![Any](./assets/any.png)

Parameter type
![Parameter](./assets/parameter-type.png)

Return type
![Return](./assets/return-type.png)

Object type
![Object](./assets/object-type.png)

Optional parameter
![Optional](./assets/optional-parameter.png)

Union type
Kết hợp của 2 hoặc nhiều type để đại diện kiểu dữ liệu cho 1 biến.
![Union](./assets/union-type.png)
Nó chỉ cho phép thực hiện những action mà hợp lệ cho tất cả các type có trong union type. Ví dụ nếu bạn có union type kiểu `string | number` thì bạn không thể thực hiện các phương thức chỉ có trên `string`:
![Working with union](./assets/work-with-union.png)
![Union solution](./assets/union-solution.png)

Alias Type (là tên đại diện cho bất cứ custom type nào)
![Alias type](./assets/alias-type.png)

Interface (cách khác để đại diện cho bất cứ custom type nào)
![Interface](./assets/interface.png)

Vậy sự khác nhau nào giữa type alias và interface?
Type alias và interface khá là giống nhau và trong nhiều trường hợp bạn có thể thoải mái lựa chọn trong việc sử dụng type hay là interface. Hầu hết những gì làm được trên interface thì type cũng làm được. Cái khác nhau lớn nhất đó là type không thể re open để add thêm properties trong khi interface thì luôn có thể extend thêm bất cứ thuộc tính nào.

Cách extend giữa type và interface

![Extend type and interface](./assets/extend-type-vs-interface.png)

Thêm thuộc tính giữa type và interface

![Add new properties type vs interface](./assets/override-properties-type-vs-interface.png)

Assertion Type
Nhiều khi bạn biết được chắc chắn thông tin về kiểu dữ liệu của 1 biến cụ thể hơn là cách mà Typescript tự detect, lúc đó bạn sẽ cần đến Assertion type.

Sử dụng với cú pháp as ....

Ví dụ dưới dây Typescript nó sẽ chỉ biết là trả về 1 HTMLElement nhưng bạn sẽ biết nó cụ thể hơn là nó thuộc HTMLElement nào, ở đây là HTMLCanvasElement
![Assertion Type](./assets/assertion-type.png)

Literal type
Nhiều khi bạn muốn cố định chính xác 1 biến có giá trị và kiểu dữ liệu là như nhau luôn, lúc đó hãy nghĩ đến literal type.

![Literal Type](./assets/literal-type.png)

Nhưng nếu biết kết hợp giữa Union type và Literal type thì sẽ trở thành 1 sự kết hợp hoàn hảo. Ví dụ như function dưới đây chỉ chấp nhận truyền vào những giá trị biết trước.

![Literal Type + Union Type](./assets/union-literal.png)

Enum type
![Enum Type](./assets/enum.png)

Typeof
Chúng ta có thể sử dụng typeof để check type của 1 biến, điều này khá hữu ích trong trường hợp check cho union type.

Intersection type
Typescript cho phép tạo ra 1 type mới kết hợp giữa các object type có sẵn

![Intersection Type](./assets/intersection.png)

Generic Type
Khi bạn muốn tạo 1 type linh động tương ứng với giá trị truyền vào, Typescript cho phép bạn làm điều đó thông qua Generic Type thay vì xác định sẵn 1 type cố định

![Generic Type](./assets/generic.png)
![Generic Use](./assets/generic-use.png)

Khai báo function generic dạng arrow:
![Generic Function Declaration](./assets/generic-function-declaration.png)

Generic class:
![Generic class](./assets/generic-class.png)

Keyof Type Operator:
Keyof nhận vào 1 object type và xử lý trả về 1 literal union type chưa key của object.
Ví dụ dưới dây P sẽ có kiểu giống như `x | y`
![Keyof type](./assets/keyof.png)

Utility Type:

Partial<Type>: biến tất cả thuộc tính của object type thành optional.
![Partial type](./assets/partial-type.png)

Required<Type>: biến tất cả thuộc tính của object type thành bắt buộc.
![Required type](./assets/required-type.png)

Readonly<Type>: biến tất cả thuộc tính của object type thành readonly nghĩa là không thể override giá trị, chỉ có thể read.
![Readonly type](./assets/readonly-type.png)

Record<Keys, Type>: dùng để map thuộc tính của object type này thành type khác.
![Record type](./assets/record-type.png)

Pick<Type, Keys>: chỉ lấy những key nào thích của 1 object type.
![Pick type](./assets/pick-type.png)

Omit<Type, Keys>: ngược lại với pick type, xóa những key nào không thích của 1 object type.
![Omit type](./assets/omit-type.png)

Exclude<UnionType, ExcludedMembers>: loại bỏ type từ union type
![Exclude type](./assets/exclude-type.png)

NonNullable<Type>: loại bỏ những type kiểu null hoặc undefined.
![NonNullable type](./assets/nonnullable-type.png)
