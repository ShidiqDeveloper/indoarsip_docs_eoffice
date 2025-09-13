# Menambahkan Data

<mark style="color:green;">`POST`</mark> `/manuscript-types`

Endpoint ini untuk menambahkan jenis naskah

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name        | Type   | Description             | Validation                |
| ----------- | ------ | ----------------------- | ------------------------- |
| `code`      | string | Kode jenis naskah       | required\|string\|max:255 |
| `name`      | string | Nama jenis naskah       | required\|string\|max:255 |
| description | string | Keterangan jenis naskah | nullable\|string\|max:300 |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan jenis naskah!",
  data: {
    id: <int>,
    code: <string>,
    name: <string>,
    description: <string>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
