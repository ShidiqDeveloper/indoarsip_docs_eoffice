# Get Sifat Naskah

<mark style="color:green;">`GET`</mark>`/manuscript-characteristics`

Endpoint ini untuk mendapatkan list sifat naskah

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                                      |
| ------- | ------ | ------------------------------------------------ |
| `limit` | number | Limitasi per halaman                             |
| `page`  | number | Filter untuk menuju halaman ke-n                 |
| name    | string | Filter untuk mencari berdasarkan nama/keterangan |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    manuscript_characteristics: [
      {
        id: <int>,
        name: <string>,
        description: <string>,
        is_active: <int>,
        created_at: <timestamp>,
        updated_at: <timestamp>,
      }
    ],
    pagination: {
      current_page: <int>,
      limit: <int>,
      total_page: <int>,
      total_data: <int>,
    }
  },
}
```
{% endtab %}
{% endtabs %}
