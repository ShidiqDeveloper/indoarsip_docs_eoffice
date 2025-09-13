# Get Data Jabatan

<mark style="color:green;">`GET`</mark>`/roles`

Endpoint ini untuk mendapatkan list jabatan yang sudah dibuat serta dengan paginasi halaman

**Query String**

| Name             | Type   | Description                      |
| ---------------- | ------ | -------------------------------- |
| limit            | number | Filter limitasi per halaman      |
| page             | number | Filter untuk menuju halaman ke-n |
| name             | string | Filter berdasarkan nama jabatan  |
| organization\_id | number | Filter berdasarkan unit kerja    |

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
    roles: [
      {
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
