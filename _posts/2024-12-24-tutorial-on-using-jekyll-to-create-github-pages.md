---
layout: post
title: "Sử dụng Jekyll để tạo GitHub Pages"
date: 2024-12-24
tags: [tag1, tag2]
---

# Sử dụng Jekyll để tạo GitHub Pages

## Giới thiệu

Jekyll là một công cụ tạo website tĩnh được hỗ trợ chính thức bởi GitHub Pages. Với Jekyll, bạn có thể dễ dàng tạo blog, website cá nhân hoặc website dự án một cách đơn giản và chuyên nghiệp.

## Cài đặt môi trường

### Yêu cầu hệ thống
- Ruby phiên bản 2.5.0 trở lên
- RubyGems
- GCC và Make
- Git

### Cài đặt Jekyll
```bash
gem install bundler jekyll
```

## Khởi tạo dự án Jekyll

### Tạo project mới
```bash
jekyll new my-blog
cd my-blog
```

### Cấu trúc thư mục
```
my-blog/
├── _config.yml
├── _data/
├── _drafts/
├── _includes/
├── _layouts/
├── _posts/
├── _sass/
├── assets/
└── index.md
```

## Cấu hình cơ bản

### File _config.yml
```yaml
# Thông tin website
title: My Blog
email: your-email@example.com
description: >-
  Write an awesome description for your new site here.
baseurl: ""
url: "https://username.github.io"

# Build settings
markdown: kramdown
theme: minima
plugins:
  - jekyll-feed
  - jekyll-seo-tag
```

## Viết bài với Jekyll

### Tạo bài viết mới
- Tạo file trong thư mục `_posts`
- Đặt tên file theo format: `YYYY-MM-DD-ten-bai-viet.md`

### Cấu trúc bài viết
```markdown
---
layout: post
title: "Tiêu đề bài viết"
date: 2024-12-24
categories: [category1, category2]
tags: [tag1, tag2]
---

Nội dung bài viết ở đây...
```

### Sử dụng Markdown
```markdown
# Tiêu đề cấp 1
## Tiêu đề cấp 2

*In nghiêng*
**In đậm**

- Danh sách không thứ tự
- Item 2
  - Item 2.1
  - Item 2.2

1. Danh sách có thứ tự
2. Item thứ 2

[Link](https://example.com)
![Hình ảnh](path/to/image.jpg)

`Code inline`

```code
Code block
```
```

## Chạy Jekyll local

### Khởi động server
```bash
bundle exec jekyll serve
```
Truy cập: http://localhost:4000

### Chế độ development
```bash
bundle exec jekyll serve --watch --livereload
```

## Triển khai lên GitHub Pages

### Tạo repository
1. Tạo repository mới trên GitHub
2. Tên repository: `username.github.io`

### Push code
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/username.github.io.git
git push -u origin main
```

### Cấu hình GitHub Pages
1. Vào Settings của repository
2. Chọn Pages trong menu bên trái
3. Source: chọn branch main
4. Folder: chọn / (root)
5. Save

## Tùy chỉnh theme

### Thêm theme mới
1. Thêm vào Gemfile:
```ruby
gem "jekyll-theme-minimal"
```

2. Cập nhật _config.yml:
```yaml
theme: jekyll-theme-minimal
```

3. Cài đặt theme:
```bash
bundle install
```

## Các lệnh Jekyll thường dùng

```bash
# Tạo site mới
jekyll new site-name

# Build site
jekyll build

# Serve với watch mode
jekyll serve --watch

# Build với môi trường production
JEKYLL_ENV=production jekyll build

# Xem version
jekyll --version
```

## Tips và lưu ý

1. **Permalink**: Tùy chỉnh URL cho bài viết
```yaml
permalink: /blog/:year/:month/:day/:title/
```

2. **Draft**: Viết bài nháp trong thư mục `_drafts`
```bash
jekyll serve --drafts
```

3. **Collections**: Tổ chức nội dung theo nhóm
```yaml
collections:
  my_collection:
    output: true
```

4. **Front Matter Defaults**: Cấu hình mặc định
```yaml
defaults:
  -
    scope:
      path: ""
      type: "posts"
    values:
      layout: "post"
      author: "Your Name"
```

## Tài liệu tham khảo

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Markdown Guide](https://www.markdownguide.org/)

*Bài viết được đăng bởi {{ site.author.name }}*
