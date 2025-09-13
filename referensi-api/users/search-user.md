# Search User

<mark style="color:green;">`GET`</mark>`/users/search`

Endpoint ini untuk mencari data users dengan default limitasi 10 dan yang status nya aktif

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name             | Type   | Description                             |
| ---------------- | ------ | --------------------------------------- |
| `keyword`        | string | Filter berdasarkan nama,email,nip,phone |
| `limit`          | number | Limitasi                                |
| role\_id         | number | Filter berdasarkan role                 |
| organization\_id | number | Filter berdasarkan unit kerjaa          |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: [
    {
      id: <int>,
      name: <string>,
      nip: <string>,
      email: <string>,
      phone: <int>,
      organization: {
        id: <int>,
        organization_name: <string>,
      },
      role: {
        id: <int>,
        role_name: <string>,
      }
    }
  ]
}
```
{% endtab %}
{% endtabs %}
