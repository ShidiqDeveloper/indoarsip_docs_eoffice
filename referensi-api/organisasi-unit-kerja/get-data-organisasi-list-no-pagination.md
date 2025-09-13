# Get Data Organisasi List (No Pagination)

<mark style="color:green;">`POST`</mark> `/prganization-units/list`

Endpoint ini untuk kebutuhan create / edit data unit kerja. Karena ada pemilihan induk unit kerja, maka dibutuhkan endpoint untuk mengambil data unit kerja.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name  | Type   | Description                                                                             |
| ----- | ------ | --------------------------------------------------------------------------------------- |
| level | string | <p>Filter berdasarkan level unit kerja. Bisa lebih dari 1. Contoh<br><br>?level=1,2</p> |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    id: <int>,
    organization_name: <string>,
    organization_code: <string>,
    short_name: <int>,
    is_active: <int>,
    level: <int>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
