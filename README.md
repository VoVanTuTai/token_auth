🔐 Simple Auth
🚀 Cách chạy
1. Vào thư mục chứa dự án
cd src/token_auth
2. Cài đặt dependencies bash Copy code: npm install express Basic Auth Chạy server bash Copy code: node app.js
Kiểm tra API
mongo trước khi đăng ký 
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/mongo.png" />
POST: http://localhost:3000/api/auth/register (đăng ký sai)
body->raw->chỉnh type sang Json nội dung "{"username":"VoVanTuTai","email":"" ,"password":"12345"}"
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/register_error_email.png" />
POST: http://localhost:3000/api/auth/register (đăng ký đúng)
body->raw->chỉnh type sang Json nội dung "{"username":"VoVanTuTai","email":"tutai@gmail.com" ,"password":"12345"}"
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/register_success.png" />
mongo sau khi đăng ký
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/mongo_after_register.png" />
POST: http://localhost:3000/api/auth/login (đăng nhập sai)
body->raw->chỉnh type sang Json nội dung "{"email":"", "password":"12345"}"
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/login_error.png" />
POST: http://localhost:3000/api/auth/login (đăng nhập sai)
body->raw->chỉnh type sang Json nội dung "{"email":"tutai@.com", "password":"12345"}"
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/login_not_found.png" />
POST: http://localhost:3000/api/auth/login (đăng nhập đúng)
body->raw->chỉnh type sang Json nội dung "{"username":"VoVanTuTai", "password":"12345"}"
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/login_success.png" />
GET: http://localhost:3000/api/auth/profile (xem profile khi không có token)
Trong tab Headers của Postman không thêm:
Key: Authorization
Value: Bearer (token vừa tạo khi đăng nhập có dấu cách sau Bearer)
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/profile_error.png" />
GET: http://localhost:3000/api/auth/profile (xem profile khi sai token)
Trong tab Headers của Postman thêm:
Key: Authorization
Value: Bearer(token vừa tạo khi đăng nhập không có dấu cách sau Bearer)
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/profile_error_token.png" />
GET: http://localhost:3000/api/auth/profile (xem profile khi đã đăng nhập thành công)
Trong tab Headers của Postman thêm:
Key: Authorization
Value: Bearer (token vừa tạo khi đăng nhập có dấu cách sau Bearer)
<img width="960" height="540" alt="3000" src="https://github.com/VoVanTuTai/token_auth/blob/main/Images_report/profile_have_token.png" />
