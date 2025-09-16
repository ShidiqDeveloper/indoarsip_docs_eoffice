# Get Data

<mark style="color:green;">`GET`</mark> `/clasification-codes`

Endpoint ini untuk mengambil list data kode klasifikasi arsip&#x20;

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                               |
| ------- | ------ | ----------------------------------------- |
| `limit` | number | Limitasi per halaman                      |
| `page`  | number | Filter halaman ke-n                       |
| keyword | string | Filter berdasarkan nama, kode, keterangan |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    clasification_codes: [
      {
        id: <int>,
        name: <string>,
        code: <string>,
        description: <string>,
        duration_active_year: <string>,
        duration_inactive_year: <string>,
        created_at: <timestamp>,
        updated_at: <timestamp>,
      }
    ],
    pagination: {
      current_page: <int>,
      limit: <int>,
      total_page: <int>,
      total_data: <int>
    }
  }
}
```
{% endtab %}
{% endtabs %}
