# Menambahkan Data

<mark style="color:green;">`POST`</mark> `/clasification-codes`

Endpoint untuk menambahkan data klasifikasi&#x20;

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                     | Type   | Description                             | Validation                        |
| ------------------------ | ------ | --------------------------------------- | --------------------------------- |
| `name`                   | string | Nama dari kode klasifikasi              | required\|string\|max:255         |
| code                     | string | Kode klasifikasi arsip                  | required\|string\|max:255\|unique |
| description              | string | Keterangan kode klasifikasi arsip       | nullable\|string\|max:300         |
| duration\_active\_year   | number | Durasi masa aktif arsip dalam tahunan   | required\|number                  |
| duration\_inactive\_year | number | Durasi masa inaktif arsip dalam tahunan | required\|number                  |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil menambahkan kode klasifikasi!",
  data: {
    id: <int>,
    name: <string>,
    code: <string>,
    description: <string>,
    duration_active_year: <string>,
    duration_inactive_year: <string>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  }
}
```
{% endtab %}
{% endtabs %}
