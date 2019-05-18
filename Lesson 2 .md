# RenderPage - hiển thị ra PartialView

## Partial View là gì?
Về cơ bản là một phần của trang web. Khi mà các đoạn code có thể tái sử dụng ở nhiều vị trí ta nên tách nó ra thành PartialView để hiển thị.

Lý do: tái sử dụng code, viết gọn hơn và nhiều tiện ích khác

Ví dụ ta có một đoạn code hiển thị sideBar mà trong layout quá dài => tạo một View dưới dạng Partial view và sử dụng bằng cách
## Cách sử dụng
### Cách 1: Render dưới dạng Static View - Truyền vào View không có dữ liệu gì cả. Thuần túy là hiển thị
Tạo view có tên là sideBar

__SideBar.cshtml__
```html
<div>Đây là sidebar</div>
```

Sử dụng partial view side bar trong một page khác
__Index.cshtml__
```html
@{
    ViewBag.Title = "Index";
    Layout = "~/Areas/Admin/Views/Shared/_Layout.cshtml"; // sử dụng section
}
<div>Đây là trang chủ</div>
@RenderPage("SideBar.cshtml") // sử dụng partial view Side bar

```
### Cách 2: Truyền dưới dạng Dynamic view
## Ứng dụng : 
