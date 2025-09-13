---
description: >-
  Endpoint ini untuk mendapatkan  data organisasi untuk kebutuhan rendering tree
  / dropdown. Semua data organisasi unit diawali dengan organisasi dengan
  parent_id NULL, sehingga akan memiliki childs
---

# Get Data Organisasi (Tree)

<mark style="color:green;">`GET`</mark>`/organization-units/tree`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: [
    {
      id: <int>,
      organization_name: <string>,
      organization_code: <string>,
      short_name: <string>,
      is_active: <int>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
      childs: [
        {
          id: <int>,
          organization_name: <string>,
          organization_code: <string>,
          short_name: <string>,
          is_active: <int>,
          created_at: <timestamp>,
          updated_at: <timestamp>,
          childs: [
            {
              id: <int>,
              organization_name: <string>,
              organization_code: <string>,
              short_name: <string>,
              is_active: <int>,
              created_at: <timestamp>,
              updated_at: <timestamp>,
              childs: []
            }
          ]
        }
      ],
    }
  ],
}
```
{% endtab %}
{% endtabs %}
