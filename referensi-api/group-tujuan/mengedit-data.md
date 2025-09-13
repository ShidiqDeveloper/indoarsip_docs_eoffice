# Mengedit Data

<mark style="color:green;">`PUT`</mark>`/group-destinations/{id_group}`

Endpoint ini untuk mengedit data grup tujuan

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
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengedit grup tujuan!",
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
