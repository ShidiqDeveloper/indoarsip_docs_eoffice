# Search Jenis Naskah

<mark style="color:green;">`GET`</mark>`/manuscript-types/search`

Endpoint untuk mencari jenis naskah yang status nya aktif

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name      | Type   | Description                             |
| --------- | ------ | --------------------------------------- |
| `keyword` | string | Cari berdasarkan nama, code, decription |

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
      code: <string>,
      name: <string>,
      description: <string>,
      is_active: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ],
}
```
{% endtab %}
{% endtabs %}
