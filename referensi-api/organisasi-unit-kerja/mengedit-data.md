---
description: Endpoint ini untuk menambahkan data organisasi / unit kerja
---

# Mengedit Data

<mark style="color:green;">`PUT`</mark>`/organization-units/{id_organization_unit}`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                | Type   | Description                 | Validation                                      |
| ------------------- | ------ | --------------------------- | ----------------------------------------------- |
| `organization_name` | string | Nama Unit Kerja             | required\|string\|max:255                       |
| `organization_code` | string | Kode Organisasi             | required\|string\|unique                        |
| short\_name         | string | Singkatan Unit Kerja        | required\|string\|unique                        |
| parent\_id          | number | Unit Induk                  | required\|number\|exists:organization\_units,id |
| is\_active          | bool   | Indikasi status aktif/tidak | sometimes\|bool                                 |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Berhasil mengedit data unit kerja!",
  data: {
    id: <int>,
    organization_name: <string>,
    organization_code: <string>,
    short_name: <int>,
    is_active: <int>,
    created_at: <timestamp>,
    updated_at: <timestamp>,
    parent: {
      id: <int>,
      organization_name: <string>,
      organization_code: <string>,
      short_name: <string>,
      is_active: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    },
  },
}
```
{% endtab %}
{% endtabs %}
