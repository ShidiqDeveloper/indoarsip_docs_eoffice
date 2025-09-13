# Menambah User

<mark style="color:green;">`POST`</mark> `/users`

Endpoint ini untuk menambah data user

**Headers**

| Name          | Value                 |
| ------------- | --------------------- |
| Content-Type  | `multipart/form-data` |
| Authorization | `Bearer <token>`      |

**Body**

```
{
  name: <string>,
  email: <string>,
  password: <string>,
  nip: <string>,
  phone: <int>,
  organization_id: <int>,
  role_id: <int>,
  user_status_id: <int>,
  photo: <file>
}
```

| Name             | Type   | Description                         | validation                                       |
| ---------------- | ------ | ----------------------------------- | ------------------------------------------------ |
| `name`           | string | Nama dari pengguna                  | required\|string\|max:255                        |
| `email`          | string | email pengguna                      | required\|email\|unique                          |
| password         | string | Password untuk masuk kedalam sistem | required\|min:6\|string\|max:100                 |
| nip              | string | Nomor Induk Pegawai                 | required\|string\|unique\|max:255                |
| phone            | number | Nomor HP Pegawari                   | required\|number\|max:20                         |
| organization\_id | number | Unit Kerja User                     | required\|number\|exists:organizxation\_units.id |
| role\_id         | number | Jabatan User                        | required\|number\|exists:roles.id                |
| user\_status\_id | number | Status user                         | required\|number\|exists:user\_statuses.id       |
| photo            | file   | Foto user                           | nullable\|file\|image\|max:5120                  |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan user!",
  data: {
    id: <int>,
    name: <string>,
    nip: <string>,
    email: <string>,
    phone: <int>,
    last_login: <timestamp>,
    organization: {
      id: <int>,
      organization_name: <string>,
    },
    role: {
      id: <int>,
      role_name: <string>,
    },
    status: {
      id: <int>,
      user_status: <string>,
    }
  },
}
```
{% endtab %}
{% endtabs %}
