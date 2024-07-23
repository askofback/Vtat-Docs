# Vtat
簡単なACLシステム<br>
[PypiでVtatを見る](https://pypi.org/project/vtat/)<br>
[他のVtatバージョンを見る](https://github.com/askofback)<br>
Vtat.js バージョン 0.0.1 ベータ

# VTAT(日本語)

## JSONの例
```json
{
    "groups": {
        "学校": [
            "group:弟と姉",
            "user:大和"
        ],
        "弟と姉": [
            "user:紬",
            "user:紬"
        ]
    }
}
```

## コードに挿入する
```javascript
<script src="https://raw.githubusercontent.com/askofback/vtat/main/vtat.js"></script>
```
または
```javascript
<script type="module" src="https://raw.githubusercontent.com/askofback/vtat/main/vtat.js"></script>
```

## 関数一覧

### addGroup(json_array, group);
`json_array`に `group`という名前のグループを追加します。<br>
そしてjsonを返します。

### removeGroup(json_array, group);
`json_array`から `group`というグループを削除します。<br>
そしてjsonを返します。

### addObject(json_array, group, name);
`group`というグループに `name`というオブジェクトを追加します。<br>
そしてjsonを返します。<br>
nameフィールドの名前は必ず `group:(グループ名)` または `user:(ユーザー名)` でなければなりません。

### eraseObject(json_array, group, name);
`group`というグループから `name`というオブジェクトを削除します。<br>
そしてjsonを返します。<br>
nameフィールドの名前は必ず `group:(グループ名)` または `user:(ユーザー名)` でなければなりません。

### userExists(json_array, group, user);
もし `group`というグループに `user`というユーザーがいる場合はtrue、いなければfalseを返しますが、この関数は使用しないでください。

### groupExists(json_array, group);
もし `group`というグループが存在する場合はtrue、存在しない場合はfalseを返します。

### meet(json_array, group, name);
もし `name`というオブジェクトが `group`というグループに属している場合はtrue、そうでない場合はfalseを返します。<br>
グループは権限を示す場合もあれば、ユーザーを示す場合もあります。<br>
nameフィールドの名前は必ず `group:(グループ名)` または `user:(ユーザー名)` でなければなりません。

### removeObject(json_array, name);
すべての場所から `name`を削除します。<br>
そしてjsonを返します。

### replaceObject(json_array, old_name, new_name);
すべての `old_name`を `new_name`に置き換えます。<br>
そしてjsonを返します。

### renameGroup(json_array, old_name, new_name);
`old_name`というグループの名前を `new_name`に変更します。<br>
そしてjsonを返します。

### renameObject(json_array, group, old_name, new_name);
`group`というグループ内で `old_name`というオブジェクトを `new_name`に変更します。<br>
そしてjsonを返します。<br>
nameフィールドの名前は必ず `group:(グループ名)` または `user:(ユーザー名)` でなければなりません。

### (ベータ) listGroups(json_array);
すべてのグループを返します。

### (ベータ) listObjects(json_array);
すべてのオブジェクトを返します。

### (ベータ) listObjectsOfGroup(json_array, group);
すべてのグループ内のオブジェクトを返します。

### (ベータ) getGroupsOfObject(json_array, name);
`name`というオブジェクトが属するすべてのグループを返します。<br>
ただし、正しく動作しない可能性があり、`group:XX`はカウントされない場合があります。

### (ベータ) objectIsInAnyGroup(json_array, name);
`name`というオブジェクトがどのグループにも属している場合はtrue、そうでない場合はfalseを返します。<br>
ただし、正しく動作しない可能性があり、`group:XX`はカウントされない場合があります。

### (ベータ) getSubgroups(json_array, group);
`group`というグループ内のサブグループを返します。
