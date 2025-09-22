# Login

<mark style="color:green;">`POST`</mark> `/login`

Endpoint untuk login kedalam sistem

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name         | Type   | Description   |
| ------------ | ------ | ------------- |
| `email`      | string | Email user    |
| `password`   | string | Password user |
| remember\_me | bool   |               |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: "Berhasil login!",
  data: {
    id: <int>,
    name: <string>,
    email: <string>,
    role: {
      id: <int>,
      role_name: <int>
    },
    token: <string>,
  }
}
```
{% endtab %}

{% tab title="404" %}
```
{
  status: false,
  status_code: 404,
  message: "User tidak ditemukan!",
  data: NULL
}
```
{% endtab %}

{% tab title="401" %}
```
{
  status: false,
  status_code: 401,
  message: "Password salah!",
  data: NULL
}
```
{% endtab %}
{% endtabs %}
