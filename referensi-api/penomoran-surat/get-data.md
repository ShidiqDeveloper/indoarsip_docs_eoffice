# Get Data

<mark style="color:green;">`POST`</mark> `/manuscript-number-formats`

Endpoint untuk mendapatkan list format nomor surat yang sudah dibuat

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                     |
| ------- | ------ | ------------------------------- |
| `limit` | number | Filter limitasi per halaman     |
| `page`  | number | Menuju halaman ke-n             |
| keyword | string | Filter berdasarkan format nomor |

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
        number_format: <string>,
        number_example: <string>,
        reset_yearly: <int>,
        is_active: <int>,
        manuscript_type: {
          id: <int>,
          name: <string>,
        },
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
