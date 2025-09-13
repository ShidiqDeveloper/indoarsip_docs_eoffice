# Mengedit Data

<mark style="color:green;">`PUT`</mark>`/manuscript-types/{id_manuscript}`

Endpoint ini untuk mengedit jenis naskah

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
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengedit jenis naskah!",
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
