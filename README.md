# MyUIT Panorama

Kho ảnh tĩnh phục vụ trình xem panorama 360° của MyUIT Campus GIS.

**GitHub Pages:** https://ducloc0802.github.io/myuit-panorama/

Trình xem Marzipano chạy trong ứng dụng MyUIT. Repository này phục vụ ảnh
chia tile và metadata qua HTTPS; không cần backend để trả ảnh.

## Dữ liệu

- 53 cảnh panorama.
- 27.083 file ảnh, tổng dung lượng khoảng 648,81 MiB.
- `tourScenes.json`: cấu hình cảnh và các mức độ phân giải.
- `tourspots.json`: các điểm tham quan.
- `dataset.json`: nguồn dữ liệu, phiên bản và thống kê.

Nguồn: [UIT-iMap/uit-imap-data](https://github.com/UIT-iMap/uit-imap-data),
commit `0e20ab5febb0b806c95282d2615cfdf295b1bd92`.
Mã nguồn iMap: [UIT-iMap/uit-imap](https://github.com/UIT-iMap/uit-imap).
Các file ảnh và JSON được giữ nguyên nội dung từ nguồn này.

## Kết nối MyUIT

Đặt biến môi trường sau trong cấu hình build của ứng dụng MyUIT:

```dotenv
CAMPUS_GIS_TILE_BASE_URL=https://ducloc0802.github.io/myuit-panorama/tiles
```

Sau khi thay đổi biến môi trường, build/deploy lại ứng dụng để cập nhật
địa chỉ ảnh. Giữ nguyên nguồn JSON/model tự chứa trong MyUIT.

Ví dụ ảnh preview:

```text
https://ducloc0802.github.io/myuit-panorama/tiles/0-cng-a/preview.jpg
```

## Xuất bản

GitHub Pages dùng nhánh `main`, thư mục `/(root)`. File `.nojekyll` rỗng
giữ nguyên cách phục vụ dữ liệu tĩnh. Kiểm tra workflow Pages sau mỗi
lần cập nhật và thử các cảnh bằng trình xem thực tế.

GitHub Pages có hạn mức dung lượng và băng thông. Theo
[tài liệu GitHub](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits),
site được xuất bản tối đa 1 GB, giới hạn mềm 100 GB băng thông/tháng.
