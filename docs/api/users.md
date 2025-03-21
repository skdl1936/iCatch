# 사용자 관리 API

## 사용자 생성
- URL: POST /api/users
- 권한: 모두
- 요청 :
{
  "username": "newuser",
  "email": "newuser@google.com",
  "password": "password123"
}
- 응답 예시:
{
  "success": true,
  "data": {
    "id": 3,
    "username": "newuser",
    "email": "newuser@google.com",
    "createdAt": "2023-01-03T00:00:00Z"

## 사용자 정보 업데이트 
- URL: PUT /api/users/{id}
- 권한: 관리자, 해당 사용자
- 요청 예시:
{
  "username": "updateduser",
  "email": "updated@google.com"
}
- 응답 예시:
{
  "success": true,
  "data": {
    "id": 1,
    "username": "updateduser",
    "email": "updated@google.com",
    "updatedAt": "2025-01-04T00:00:00Z"
  },
  "error": null
}

## 사용자 삭제
- URL: DELETE /api/users/{id}
- 권한: 관리자, 해당 사용자
- 응답 예시:
{
  "success": true,
  "data": {
    "message": "사용자가 삭제되었습니다."
  },
  "error": null
}

## 비밀번호 변경 
- URL: POST /api/users/{id}/change-password
- 권한: 관리자, 해당 사용자
- 요청 예시:
{
  "currentPassword": "oldpassword123",
  "newPassword": "newpassword456",
  "confirmPassword": "newpassword456"
}
- 응답 예시:
{
  "success": true,
  "data": {
    "message": "비밀번호가 변경되었습니다."
  },
  "error": null
}
## 로그인 
- URL: POST /api/auth/login
- 권한: 모두
- 요청 예시:
{
  "email": "user1@google.com",
  "password": "password123"
}
- 응답 예시:
{
  "success": true,
  "data": {
    "token": ".......",
    "user": {
      "id": 1,
      "username": "user1",
      "email": "user1@google.com"
    }
  },
  "error": null
}

## 로그아웃
- URL: POST /api/auth/logout
- 권한: 인증된 사용자
- 응답 예시:
{
  "success": true,
  "data": {
    "message": "로그아웃되었습니다."
  },
  "error": null
}

## 사용자 목록 조회
- URL : api/users
- 권한: 관리자
- 응답 예시:
```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "username": "user1",
      "email": "user1@google.com",
      "createdAt": "2025-01-01T00:00:00Z"
    },
    {
      "id": 2,
      "username": "user2",
      "email": "user2@google.com",
      "createdAt": "2025-01-02T00:00:00Z"
    }
  ],
  "error": null
}

## 사용자 상세 조회
- URL: GET /api/users/{id}
- 권한: 관리자, 사용자
- 응답 예시:
{
  "success": true,
  "data": {
    "id": 1,
    "username": "user1",
    "email": "user1@google.com",
    "createdAt": "2025-01-01T00:00:00Z"
  },
  "error": null
}

## 사용자 디바이스 조회
- URL: GET /api/users/{id}/devices
- 권한: 관리자, 해당 사용자
- 응답 예시:
{
  "success": true,
  "data": [
    {
      "id": 1,
      "deviceName": "거실 카메라",
      "macAddress": "00:11:22:33:44:55",
      "status": "on",
      "lastConnection": "2025-01-04T10:15:00Z"
    },
  "error": null
}
## 토큰 갱신
- URL: POST /api/auth/refresh-token
- 권한: 인증된 사용자
- 요청 예시:
{
  "refreshToken": "......"
}
- 응답 예시:
{
  "success": true,
  "data": {
    "token": "......",
    "refreshToken": "......"
  },
  "error": null
}
