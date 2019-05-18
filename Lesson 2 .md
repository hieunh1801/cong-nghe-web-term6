 # RenderSection - hiển thị section
- Trong trang Layout/MasterLayout => ta tạo các vùng để nhúng Section vào

__Layout.cshtml__
```html
<body>
    <!-- Page level custom scripts -->
    <script src="~/Assets/Admin/js/demo/chart-area-demo.js"></script>
    <script src="~/Assets/Admin/js/demo/chart-pie-demo.js"></script>
    @RenderSection("ClientScript", false); 
    // nếu để true thì tất cả các trang sử dụng layout này phải có section này. Nếu không có thì nó sẽ báo lỗi
    // Để false thì tùy chọn có cũng được mà không có cũng đuọc
</body>
```
- Khi một file áp dụng layout trên, ta muốn chèn các đoạn section vào thì sẽ làm như sau
__Index.cshtml__
```html
@{
    ViewBag.Title = "Index";
    Layout = "~/Areas/Admin/Views/Shared/_Layout.cshtml"; // sử dụng section
}
<div>Đây là trang chủ</div>
@section ClientScript 
{
    // chèn code vào đây để sử dụng trong section
}
```

## Ứng dụng: 
Trong trang chủ nhiều khi ta muốn hiển thị thêm phần danh mục, trang chi tiết sản phẩm lại không có mà ta lại muốn cả 2 dùng chung Layout. Thế nên là ta chèn trước ở trang chủ một đoạn section là category. Sau đó trang nào muốn có Category thì ta chèn category vào đó