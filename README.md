![Mastodon](https://i.imgur.com/NhZc40l.png)
========

[![GitHub release](https://img.shields.io/github/release/mastodon/mastodon.svg)][releases]
[![Build Status](https://img.shields.io/circleci/project/github/mastodon/mastodon.svg)][circleci]
[![Code Climate](https://img.shields.io/codeclimate/maintainability/mastodon/mastodon.svg)][code_climate]
[![Crowdin](https://d322cqt584bo4o.cloudfront.net/mastodon/localized.svg)][crowdin]
[![Docker Pulls](https://img.shields.io/docker/pulls/tootsuite/mastodon.svg)][docker]

[releases]: https://github.com/mastodon/mastodon/releases
[circleci]: https://circleci.com/gh/mastodon/mastodon
[code_climate]: https://codeclimate.com/github/mastodon/mastodon
[crowdin]: https://crowdin.com/project/mastodon
[docker]: https://hub.docker.com/r/tootsuite/mastodon/

Mastodon là một **server mạng xã hội miễn phí, mã nguồn mở** dựa trên ActivityPub nơi mà người dùng có thể theo dõi bạn bè và khám phá những người bạn mới. Tại Mastodon, người dùng có thể đăng tải mọi thứ mình muốn: link, hình ảnh, chữ viết, video. Tất cả các server của Mastodon đều có thể tương tác như một mạng liên hợp (người dùng trên một server có thể liên lạc với người dùng trên server khác, kể cả những phần mềm  không phải mastodon mà sử dụng ActivityPub)!

Bấm vào bên dưới để  **biết thêm** bằng cách xem video giới thiệu:

[![Screenshot](https://blog.joinmastodon.org/2018/06/why-activitypub-is-the-future/ezgif-2-60f1b00403.gif)][youtube_demo]

[youtube_demo]: https://www.youtube.com/watch?v=IPSbNdBmWKE

## Navigation

- [Trang chủ dự án 🐘](https://joinmastodon.org)
- [Xem nhà tài trợ](https://joinmastodon.org/sponsors)
- [Blog](https://blog.joinmastodon.org)
- [Documentation](https://docs.joinmastodon.org)
- [Xem các server Mastodon](https://joinmastodon.org/#getting-started)
- [Xem các ứng dụng Mastodon](https://joinmastodon.org/apps)



## Tính năng

<img src="https://docs.joinmastodon.org/elephant.svg" align="right" width="30%" />

**Không bị khóa nhà cung cấp: Hoàn toàn tương thích với những nền tảng ActivityPub**

Không cần phải là Mastodon, phần mềm nào sử dụng ActivityPub cũng là một phần của mạng xã hội! [Xem thêm](https://blog.joinmastodon.org/2018/06/why-activitypub-is-the-future/)

**Dòng thời gian cập nhật theo thời gian thực, đúng thứ tự**

Những cập nhật của những người bạn theo dõi sẽ được cập nhật theo thời gian thực trong Giao Diện bằng Websocket!

**Đa phương tiện như hình ảnh và video ngắn**

Tải lên và xem hình ảnh và video dạng WebM/MP4 gắn với những bài đăng của bạn. Video không có âm thanh sẽ được xử lý như GIF;video thường sẽ được phát đi phát lại - như vines vậy!

**Các công cụ an toàn và giám sát**

Bài đăng riêng tư, khóa tài khoản, lọc cụm từ, bỏ xem bài viết, chặn và nhiều chức năng khác, cùng với đó là một hệ thống tố cáo và kiểm duyệt. [Xem thêm](https://blog.joinmastodon.org/2018/07/cage-the-mastodon/)

**OAuth2 và một REST API đơn giản**

Mastodon cso thể được dùng như một nhà cung cấp OAuth2 nên các ứng dụng bên thứ ba có thể sử dụng API REST và Streaming, mang lại một hệ sinh thái ứng dụng đa dạng với nhiều lựa chọn!

## Vận hành

**Tech Stack:**

- **Ruby on Rails** chạy REST API và một vài trang web
- **React.js** và Redux được sử dụng cho phần động (dynamic) của giao diện 
- **Node.js** dùng để chạy API Streaming

**Yêu cầu:**

- **PostgreSQL** 9.5+
- **Redis** 4+
- **Ruby** 2.5+
- **Node.js** 12+

Repository bao gồm cấu hình vận hành cho **Docker và docker-compose**, và vài nền tảng thường gặp như **Heroku**, **Scalingo**, và **Nanobox**. Hướng dẫn [cài đặt **cơ bản**](https://docs.joinmastodon.org/admin/install/) is available in the documentation.

Một cấu hình **Vagrant** đã được thêm vào cho mục đích phát triển. Hướng dẫn sử dụng:

- Cài đặt Vagrant và Virtualbox
- Chạy `vagrant up`
- Chạy `vagrant ssh -c "cd /vagrant && foreman start"`
- Mở `http://mastodon.local` trong trình duyệt của bạn

## Đóng góp

Mastodon là **phần mềm miễn phí, mã nguồn mở** có giấy phép **AGPLv3**.

Bản fork này là dự án của nhóm Mastodon, thực hiện cho môn học Phát triển phần mềm mã nguồn mở - SE301.M11, học kì II năm học 2021-2022, Đại học Công nghệ Thông tin - ĐH Quốc gia TP.HCM
## License

Copyright (C) 2016-2021 Eugen Rochko & other Mastodon contributors (see [AUTHORS.md](AUTHORS.md))

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program. If not, see <https://www.gnu.org/licenses/>.
