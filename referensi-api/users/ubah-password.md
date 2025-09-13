# Ubah Password

<mark style="color:green;">`PUT`</mark>`/users/{id_user}/change-password`&#x20;

Endpoint ini untuk merubah password user by admin

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

```
{
  password: <string>,
  password_confirmation: <string>
}
```

| Name                   | Type   | Description                   | Validation                        |
| ---------------------- | ------ | ----------------------------- | --------------------------------- |
| `password`             | string | Password baru user            | required\|min:\|confimed\|max:100 |
| password\_confirmation | string | Konfirmasi password baru user | required\|min:\|confimed\|max:100 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengubah password user!",
  data: null,
}
```
{% endtab %}
{% endtabs %}

