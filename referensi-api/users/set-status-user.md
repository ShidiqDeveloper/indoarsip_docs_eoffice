# Set status user

<mark style="color:green;">`PUT`</mark>`/`users/{user\_id}/status/{status\_id}

Endpoint untuk menandakan status user

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengubah status user!",
  data: null,
}
```
{% endtab %}
{% endtabs %}
