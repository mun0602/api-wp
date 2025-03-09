# api-wp# WordPress REST API - Tổng quan và ví dụ lệnh

| Chức năng | Mô tả | Endpoint | Phương thức | Ví dụ |
|-----------|-------|----------|-------------|-------|
| **Quản lý bài viết** |
| Lấy danh sách bài viết | Truy xuất danh sách bài viết với nhiều tùy chọn lọc | `/wp/v2/posts` | GET | `GET /wp-json/wp/v2/posts?per_page=5&orderby=date&order=desc` |
| Lấy chi tiết bài viết | Lấy thông tin chi tiết của một bài viết cụ thể | `/wp/v2/posts/<id>` | GET | `GET /wp-json/wp/v2/posts/123` |
| Tạo bài viết | Đăng một bài viết mới | `/wp/v2/posts` | POST | `POST /wp-json/wp/v2/posts` với JSON `{"title":"Bài viết mới","content":"Nội dung","status":"publish"}` |
| Cập nhật bài viết | Chỉnh sửa một bài viết đã tồn tại | `/wp/v2/posts/<id>` | PUT/PATCH | `PUT /wp-json/wp/v2/posts/123` với JSON `{"title":"Tiêu đề đã cập nhật"}` |
| Xóa bài viết | Xóa một bài viết | `/wp/v2/posts/<id>` | DELETE | `DELETE /wp-json/wp/v2/posts/123` |
| **Quản lý trang** |
| Lấy danh sách trang | Truy xuất danh sách các trang | `/wp/v2/pages` | GET | `GET /wp-json/wp/v2/pages` |
| Lấy chi tiết trang | Lấy thông tin chi tiết của một trang cụ thể | `/wp/v2/pages/<id>` | GET | `GET /wp-json/wp/v2/pages/45` |
| Tạo trang | Đăng một trang mới | `/wp/v2/pages` | POST | `POST /wp-json/wp/v2/pages` với JSON `{"title":"Trang giới thiệu","content":"Nội dung","status":"publish"}` |
| Cập nhật trang | Chỉnh sửa một trang đã tồn tại | `/wp/v2/pages/<id>` | PUT/PATCH | `PUT /wp-json/wp/v2/pages/45` với JSON `{"title":"Trang liên hệ mới"}` |
| Xóa trang | Xóa một trang | `/wp/v2/pages/<id>` | DELETE | `DELETE /wp-json/wp/v2/pages/45` |
| **Quản lý phương tiện** |
| Lấy danh sách media | Truy xuất danh sách tệp phương tiện | `/wp/v2/media` | GET | `GET /wp-json/wp/v2/media` |
| Tải lên media mới | Tải lên hình ảnh, video, hoặc tệp khác | `/wp/v2/media` | POST | `POST /wp-json/wp/v2/media` với header `Content-Disposition: attachment; filename=image.jpg` |
| Xóa media | Xóa một tệp phương tiện | `/wp/v2/media/<id>` | DELETE | `DELETE /wp-json/wp/v2/media/78` |
| **Quản lý chuyên mục và thẻ** |
| Lấy danh sách chuyên mục | Truy xuất danh sách các chuyên mục | `/wp/v2/categories` | GET | `GET /wp-json/wp/v2/categories` |
| Tạo chuyên mục mới | Tạo một chuyên mục mới | `/wp/v2/categories` | POST | `POST /wp-json/wp/v2/categories` với JSON `{"name":"Chuyên mục mới","description":"Mô tả"}` |
| Lấy danh sách thẻ | Truy xuất danh sách các thẻ | `/wp/v2/tags` | GET | `GET /wp-json/wp/v2/tags` |
| Tạo thẻ mới | Tạo một thẻ mới | `/wp/v2/tags` | POST | `POST /wp-json/wp/v2/tags` với JSON `{"name":"Thẻ mới"}` |
| **Quản lý người dùng** |
| Lấy danh sách người dùng | Truy xuất danh sách người dùng | `/wp/v2/users` | GET | `GET /wp-json/wp/v2/users` |
| Lấy thông tin người dùng | Lấy thông tin chi tiết của một người dùng | `/wp/v2/users/<id>` | GET | `GET /wp-json/wp/v2/users/1` |
| Tạo người dùng mới | Tạo một tài khoản người dùng mới | `/wp/v2/users` | POST | `POST /wp-json/wp/v2/users` với JSON `{"username":"newuser","email":"user@example.com","password":"secure_pass"}` |
| Cập nhật người dùng | Chỉnh sửa thông tin người dùng | `/wp/v2/users/<id>` | PUT/PATCH | `PUT /wp-json/wp/v2/users/5` với JSON `{"first_name":"Tên mới"}` |
| **Bình luận** |
| Lấy danh sách bình luận | Truy xuất danh sách bình luận | `/wp/v2/comments` | GET | `GET /wp-json/wp/v2/comments` |
| Đăng bình luận mới | Đăng một bình luận mới | `/wp/v2/comments` | POST | `POST /wp-json/wp/v2/comments` với JSON `{"post":123,"content":"Bình luận mới","author_name":"Người đọc"}` |
| Phê duyệt bình luận | Chuyển trạng thái bình luận thành đã phê duyệt | `/wp/v2/comments/<id>` | PATCH | `PATCH /wp-json/wp/v2/comments/42` với JSON `{"status":"approved"}` |
| **Tùy biến** |
| Tùy chỉnh menu | Truy xuất các menu và mục menu (với plugin) | `/wp-api-menus/v2/menus` | GET | `GET /wp-json/wp-api-menus/v2/menus` |
| Lấy các tùy chỉnh | Truy xuất dữ liệu từ Theme Customizer | `/wp/v2/settings` | GET | `GET /wp-json/wp/v2/settings` |
| **Plugin và giao diện** |
| Kiểm tra plugin đã cài đặt | Truy xuất danh sách plugin (cần quyền) | `/wp/v2/plugins` | GET | `GET /wp-json/wp/v2/plugins` |
| Kích hoạt plugin | Kích hoạt một plugin cụ thể | `/wp/v2/plugins/<plugin>` | PUT | `PUT /wp-json/wp/v2/plugins/akismet/akismet.php` với JSON `{"status":"active"}` |
| **Tìm kiếm** |
| Tìm kiếm nội dung | Tìm kiếm nội dung trên toàn trang | `/wp/v2/search` | GET | `GET /wp-json/wp/v2/search?search=từ khóa` |
| **Xác thực và trạng thái** |
| Xác thực JWT | Lấy token JWT cho các yêu cầu xác thực (cần plugin) | `/jwt-auth/v1/token` | POST | `POST /wp-json/jwt-auth/v1/token` với JSON `{"username":"admin","password":"pass"}` |
| Kiểm tra trạng thái | Lấy thông tin về cài đặt và trạng thái site | `/` | GET | `GET /wp-json/` |
| **Taxonomy tùy chỉnh** |
| Lấy taxonomy tùy chỉnh | Truy xuất dữ liệu từ taxonomy tùy chỉnh | `/wp/v2/<taxonomy>` | GET | `GET /wp-json/wp/v2/product_category` |
| **Custom Post Types** |
| Lấy danh sách CPT | Truy xuất danh sách các bài viết thuộc custom post type | `/wp/v2/<post_type>` | GET | `GET /wp-json/wp/v2/products` |
| Tạo bài CPT mới | Tạo mục mới trong custom post type | `/wp/v2/<post_type>` | POST | `POST /wp-json/wp/v2/products` với JSON `{"title":"Sản phẩm mới","content":"Mô tả"}` |
| **Custom Endpoints** |
| API tùy chỉnh | Truy cập endpoint API tùy chỉnh | `/custom-namespace/v1/route` | GET/POST | `GET /wp-json/my-shop/v1/featured-products` |
| **WooCommerce** (với plugin WC REST API) |
| Lấy danh sách sản phẩm | Truy xuất sản phẩm WooCommerce | `/wc/v3/products` | GET | `GET /wp-json/wc/v3/products` |
| Tạo đơn hàng | Tạo một đơn đặt hàng mới | `/wc/v3/orders` | POST | `POST /wp-json/wc/v3/orders` với JSON đơn hàng |

## Ví dụ code truy cập WordPress REST API

### JavaScript (Fetch API)

```javascript
// Lấy 5 bài viết mới nhất
fetch('https://example.com/wp-json/wp/v2/posts?per_page=5')
  .then(response => response.json())
  .then(posts => console.log(posts))
  .catch(error => console.error(error));

// Đăng bài viết mới (với xác thực)
const token = 'your_jwt_token';
fetch('https://example.com/wp-json/wp/v2/posts', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer ' + token
  },
  body: JSON.stringify({
    title: 'Bài viết từ API',
    content: 'Nội dung bài viết',
    status: 'publish'
  })
})
.then(response => response.json())
.then(data => console.log('Bài viết đã được tạo:', data))
.catch(error => console.error(error));
```

### PHP

```php
// Lấy danh sách bài viết
$response = wp_remote_get('https://example.com/wp-json/wp/v2/posts?per_page=5');
if (!is_wp_error($response)) {
  $posts = json_decode(wp_remote_retrieve_body($response));
  print_r($posts);
}

// Đăng bài viết mới (với Basic Auth)
$username = 'your_username';
$password = 'your_password';
$credentials = base64_encode($username . ':' . $password);

$response = wp_remote_post('https://example.com/wp-json/wp/v2/posts', array(
  'headers' => array(
    'Authorization' => 'Basic ' . $credentials,
    'Content-Type' => 'application/json'
  ),
  'body' => json_encode(array(
    'title' => 'Bài viết mới từ PHP',
    'content' => 'Nội dung bài viết',
    'status' => 'publish'
  ))
));

if (!is_wp_error($response)) {
  $data = json_decode(wp_remote_retrieve_body($response));
  echo 'Bài viết đã được tạo với ID: ' . $data->id;
}
```

### Python (với thư viện requests)

```python
import requests
import json

# Lấy danh sách bài viết
response = requests.get('https://example.com/wp-json/wp/v2/posts?per_page=5')
posts = response.json()
print(posts)

# Đăng bài viết mới (với xác thực)
username = 'your_username'
password = 'your_password'
credentials = (username, password)

post_data = {
    'title': 'Bài viết từ Python',
    'content': 'Nội dung bài viết',
    'status': 'publish'
}

response = requests.post(
    'https://example.com/wp-json/wp/v2/posts',
    auth=credentials,
    headers={'Content-Type': 'application/json'},
    data=json.dumps(post_data)
)

if response.status_code == 201:  # Created
    new_post = response.json()
    print(f'Bài viết đã được tạo với ID: {new_post["id"]}')
else:
    print(f'Lỗi: {response.status_code} - {response.text}')
```

## Lưu ý quan trọng khi sử dụng WordPress REST API

1. **Xác thực**: Hầu hết các hoạt động ghi (POST, PUT, DELETE) đều yêu cầu xác thực
2. **Phân quyền**: API tuân theo hệ thống phân quyền của WordPress
3. **Rate Limiting**: Một số host giới hạn số lượng yêu cầu API
4. **Bảo mật**: Luôn sử dụng HTTPS và quản lý cẩn thận thông tin xác thực
5. **Tùy chỉnh**: API có thể được mở rộng với endpoint tùy chỉnh thông qua plugin hoặc code
