[<-](https://github.com/askofback/Vtat-Docs/blob/main/README.md)
# Vtat
간단한 ACL 시스템<br>
[Pypi에서 Vtat 보기](https://pypi.org/project/vtat/)<br>
[다른 Vtat 버전들 보기](https://github.com/askofback)<br>
Vtat.js 버전 0.0.1 베타
# VTAT(한국어)
## JSON 예제
```json
{
"모임": {
  "학교": [
    "group:철수 남매",
    "user:길동"
  ],
  "철수 남매": [
    "user:철수",
    "user:영희"
  ],
}
}
```
## 코드에 넣기
```javascript
<script src="https://raw.githubusercontent.com/askofback/vtat/main/vtat.js">
```
아니면
```javascript
<script type="module" src="https://raw.githubusercontent.com/askofback/vtat/main/vtat.js">
```
## 함수 목록
### addGroup(json_array, group);
`json_array`에 `group`이라는 이름을 가진 모임을 추가합니다.
그리고 json을 반환합니다.
### removeGroup(json_array, group);
`json_array`에서 `group`이라는 모임을 제거합니다.
그리고 json을 반환합니다.
### addObject(json_array, group, name);
`group`이라는 모임에 `name`이라는 개체를 추가합니다.
그리고 json을 반환합니다.
name칸의 이름은 무조건 `group:(모임 이름)` 또는 `user:(유저 이름)`이어야 합니다.
### eraseObject(json_array, group, name);
`group`이라는 모임에서 `name`이라는 개체를 제거합니다.
그리고 json을 반환합니다.
name칸의 이름은 무조건 `group:(모임 이름)` 또는 `user:(유저 이름)`이어야 합니다.
### userExists(json_array, group, uesr);
만약 `group`이라는 모임속에 `user`라는 사용자가 있다면 참 아니라면 거짓을 반환하지만
이 함수를 사용하지 마세요.
### groupExists(json_array, group);
만약`group`이라는 모임이 있다면 참 아니라면 거짓을 반환합니다.
### meet(json_array, group, name);
만약 `name`이라는 개체가 해당 `group`이라는 모임에 속해있다면 참,
아니라면 거짓을 반환합니다.
참고로 모임은 권한을 나타낼 수도 있고 사용자들을 나타낼 수도 있습니다.
name칸의 이름은 무조건 `group:(모임 이름)` 또는 `user:(유저 이름)`이어야 합니다.
### removeObject(json_array, name);
모든 곳에서 `name`을 제거합니다.
그리고 json을 반환합니다.
### replaceObject(json_array, old_name, new_name);
모든 `old_name`을 `new_name`으로 대체합니다.
그리고 json을 반환합니다.
### renameGroup(json_array, old_name, new_name);
`old_name`이라는 모임의 이름을 `new_name`으로 바꿉니다.
그리고 json을 반환합니다.
### renameObject(json_array, group, old_name, new_name);
`group`이라는 모임 속에서 `old_name`이라는 개체를 `new_name`으로 바꿉니다.
그리고 json을 반환합니다.
name칸의 이름은 무조건 `group:(모임 이름)` 또는 `user:(유저 이름)`이어야 합니다.
### (베타) listGroups(json_array);
모든 모임을 반환합니다.
### (베타) listObjects(json_array);
모든 개체를 반환합니다.
### (베타) listObjectsOfGroup(json_array, group);
모든 모임속 개체를 반환합니다.
### (베타) getGroupsOfObject(json_array, name);
`name`이라는 개체가 속한 모든 몽임을 반환합니다.
단 제대로 작동하지 않을 수 있으며 `group:XX`는 카운트 되지 않을 수 있습니다.
### (베타) objectIsInAnyGroup(json_array, name);
`name`이라는 개체가 어느 모임에나 있다면 참 아니라면 거짓을 반환합니다.
단 제대로 작동하지 않을 수 있으며 `group:XX`는 카운트 되지 않을 수 있습니다.
### (베타) getSubgroups(json_array, group);
`group`이라는 모임속 하위 모임들을 반환합니다.
