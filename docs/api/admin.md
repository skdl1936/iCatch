# 사용자 계정 관리 API

## 사용자 정보 업데이트 
- **URL**: PUT /api/admin/users/{id}
- **권한**: 관리자, 해당 사용자
- **요청 예시**:
```json
{
  "username": "updateduser",
  "email": "updated@google.com"
}
```
- **응답 예시**:
```json
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
```

## 사용자 삭제
- **URL**: DELETE /api/admin/users/{id}
- **권한**: 관리자, 해당 사용자
- **응답 예시**:
```json
{
  "success": true,
  "data": {
    "message": "사용자가 삭제되었습니다."
  },
  "error": null
}
```

## 사용자 권한 변경
- **URL**: DELETE /api/admin/users/{id}
- **권한**: 관리자
- **응답 예시**:
```json
{
  "success": true,
  "data": {
    "message": "사용자가 삭제되었습니다."
  },
  "error": null
}
```
# IoT 상태 API
## IoT 시스템 상태 업데이트
- **URL**: POST /api/admin/iot/status
- **권한**: 관리자
- **요청 예시**:
```json
{
  "id": 123,
  "status": "active",
  "temperature": 25.3,
  "humidity": 60
}
```
- **응답 예시**:
```json
{
  "success": true,
  "data": {
    "id": 123,
    "status": "active",
    "temperature": 25.3,
    "humidity": 60,
    "updatedAt": "2025-03-09T12:01:00Z"
  },
  "error": null
}
```
## IoT 시스템 상태 모니터링
- **URL**: GET /api/admin/iot/status/{id}
- **권한**: 관리자
- **응답 예시**:
```json
{
  "success": true,
  "data": {
    "id": 123,
    "status": "active",
    "temperature": 25.3,
    "humidity": 60,
    "updatedAt": "2025-03-09T12:01:00Z"
  },
  "error": null
}
```
# 시스템 관리 API
## 시스템 업데이트 관리(버전 확인) -- 이거는 라즈베리파이에서도 요청을 보내야함
- **URL**: POST /api/admin/system/update
- **권한**: 관리자
- **요청 예시**:
```json
{
  "version": 123,
  "status": "active",
  "temperature": 25.3,
  "humidity": 60
}
```
- **응답 예시**:
```json
{
  "success": true,
  "data": {
    "id": 123,
    "status": "active",
    "temperature": 25.3,
    "humidity": 60,
    "updatedAt": "2025-03-09T12:01:00Z"
  },
  "error": null
}



