# Get Jenis Naskah

<mark style="color:green;">`GET`</mark>`/manuscript-types`

Endpoint ini untuk mendapatkan list jenis naskah

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                                           |
| ------- | ------ | ----------------------------------------------------- |
| `limit` | number | Limitasi per halaman                                  |
| `page`  | number | Filter untuk menuju halaman ke-n                      |
| name    | string | Filter untuk mencari berdasarkan nama/kode/keterangan |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    manuscript_types: [
      {
        id: <int>,
        code: <string>,
        name: <string>,
        description: <string>,
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
