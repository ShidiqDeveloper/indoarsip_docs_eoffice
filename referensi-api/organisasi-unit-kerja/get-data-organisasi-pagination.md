---
description: >-
  Endpoint ini untuk mendapatkan list organisasi / unit kerja dengan paginasi
  tanpa child atau apapun namun dengan dimuilai level 2
---

# Get Data Organisasi (Pagination)

<mark style="color:green;">`GET`</mark>`/organization-units/paginated`

**Query String**

| Name  | Description                 |
| ----- | --------------------------- |
| limit | Limitasi Per Halaman Berapa |
| page  | Filter halaman ke berapa    |

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
  data: {
    organization_units: [
      {
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
      }
    ],
    pagination: {
      current_page: <int>,
      limit: <int>,
      total_page: <int>,
      total_data: <int>,
    }
  },
}

```
{% endtab %}
{% endtabs %}
