# Set status

<mark style="color:green;">`PUT`</mark>`/manuscript-types`/{id}/status/{status\_id}

Endpoint untuk menandakan status

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
  message: "Berhasil mengubah status jenis naskah!",
  data: null,
}
```
{% endtab %}
{% endtabs %}
