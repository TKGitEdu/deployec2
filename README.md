# deployec2
# 1. Cập nhật code + chạy lại
git pull origin main
docker compose -f docker-compose.prod.yml up -d --build

# 2. Dừng tạm (debug, bảo trì)
docker compose -f docker-compose.prod.yml stop

# 3. Khởi động lại
docker compose -f docker-compose.prod.yml start

# 4. Dừng + DỌN SẠCH (deploy mới)
docker compose -f docker-compose.prod.yml down
# 2️⃣ Xoá toàn bộ container cũ, image cũ (tuỳ chọn nếu muốn pull lại)
docker system prune -af