# Mengedit Data

<mark style="color:green;">`POST`</mark> `/manuscript-characteristics/{id}`

Endpoint ini untuk mengedit sifat naskah

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name        | Type   | Description                  | Validation                  |
| ----------- | ------ | ---------------------------- | --------------------------- |
| `name`      | string | Nama jenis naskah            | required\|string\|max:255   |
| description | string | Keterangan jenis naskah      | nullable\|string\|max:300   |
| is\_active  | number | Indikasi status jenis naskah | required\|number\|enum(1,0) |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengedit sifat naskah!",
  data: {
    id: <int>,
    name: <string>,
    description: <string>,
    is_active: <int>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
