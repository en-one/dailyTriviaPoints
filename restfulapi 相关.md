## restfulapi 相关

### 一、协议

---

总是使用HTTPS协议



### 二、域名

---

应尽量将api部署到专用域名下

> ```
> https://api.example.com
> ```

如果确定API很简单，不会有进一步扩展，可以考虑放在主域名下。

> ```javascript
> https://example.org/api/
> ```



### 三、版本

---

应将API的版本号放入URL

```
https://api.example.com/v1/
```



### 四、路径

---

API网址：每个网址代表一种资源，所以网址中不能有动词，一般适用名词复数（和数据库表对应）

举例：API提供动物园（zoo）的信息，还包括各种动物和雇员的信息，路径设计：

> - https://api.example.com/v1/zoos
> - https://api.example.com/v1/animals
> - https://api.example.com/v1/employees



### 五、HTTP动词

---

常用动词

> - GET（SELECT）：从服务器取出资源（一项或多项）。
> - POST（CREATE）：在服务器新建一个资源。名词化动作执行
> - PUT（UPDATE）：修改实体资源的全属性
> - PATCH（UPDATE）：修改实体资源的部分属性
> - DELETE（DELETE）：从服务器删除资源。

举例：

> - GET /zoos：列出所有动物园
> - POST /zoos：新建一个动物园
> - GET /zoos/ID：获取某个指定动物园的信息
> - PUT /zoos/ID：更新某个指定动物园的信息（提供该动物园的全部信息）
> - PATCH /zoos/ID：更新某个指定动物园的信息（提供该动物园的部分信息）
> - DELETE /zoos/ID：删除某个动物园
> - GET /zoos/ID/animals：列出某个指定动物园的所有动物
> - DELETE /zoos/ID/animals/ID：删除某个指定动物园的指定动物



### 六、过滤信息

如果记录数量很多，服务器不可能都将它们返回给用户。API应该提供参数，过滤返回结果。

下面是一些常见的参数。

> - ?limit=10：指定返回记录的数量
> - ?offset=10：指定返回记录的开始位置。
> - ?page=2&per_page=100：指定第几页，以及每页的记录数。
> - ?sortby=name&order=asc：指定返回结果按照哪个属性排序，以及排序顺序。
> - ?animal_type_id=1：指定筛选条件

参数的设计允许存在冗余，即允许API路径和URL参数偶尔有重复。比如，GET /zoo/ID/animals 与 GET /animals?zoo_id=ID 的含义是相同的。

## 七、项目示例

1. url里面都用名词，由context-path和url组成
2. context-path用版本/服务名格式, 如v1/usermanager
3. url表示的是实体资源，如用户，或者动作的名词化

---

原文：https://www.ruanyifeng.com/blog/2014/05/restful_api.html
