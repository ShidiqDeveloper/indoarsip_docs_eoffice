# Menambahkan Data

<mark style="color:green;">`POST`</mark> `/group-destinations`

Endpoint ini untuk menambahkan data grup tujuan

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body / Payload**

```
{
  group_name: <string>,
  group_description: <string>,
  is_active: <bool>,
  users: [<int>, ...],
}
```

| Name                | Type   | Description                                  | Validation                       |
| ------------------- | ------ | -------------------------------------------- | -------------------------------- |
| `group_name`        | string | Nama dari grup tujuan                        | required\|string\|\|max:255      |
| `group_description` | string | Keterangan grup                              | required\|string\|\|max:255      |
| is\_active          | bool   | Indikasi status aktif/tidak grup             | sometimes\|bool                  |
| users               | array  | User siapa saja yang dimasukan kedalam group | required\|array\|exists:users.id |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan grup tujuan!",
  data: {
    id: <int>,
    group_name: <string>,
    group_description: <string>,
    is_active: <int>,
    count_user: <int>,
    user_create: {
      id: <int>,
      name: <string>,
    },
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
