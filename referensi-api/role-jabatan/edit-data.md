# Edit Data

<mark style="color:green;">`PUT`</mark>`/roles/{id_role}`

Endpoint untuk mengedit data role / jabatan

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name              | Type   | Description                           | Validation                                       |
| ----------------- | ------ | ------------------------------------- | ------------------------------------------------ |
| `role_name`       | string | Nama role / jabatan                   | required\|string\|max:255                        |
| `organization_id` | number | Jataban termasuk dari unit kerja mana | required\|number\|exists:organization\_units.id  |
| level\_access\_id | number | Level Akses Jabatan                   | required\|number\|exists:level\_access\_roles.id |
| is\_active        | bool   | Penanda status keaktifan role/jabatan | sometimes\|bool                                  |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengedit data jabatan!",
  data: {
    id: <int>,
    role_name: <string>,
    is_active: <int>,
    level_access: {
      id: <int>,
      level_access: <string>,
    },
    organization_unit: {
      id: <int>,
      organization_name: <string>,
    },
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
