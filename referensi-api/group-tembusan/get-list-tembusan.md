# Get List Tembusan

<mark style="color:green;">`GET`</mark>`/group-passthroughs`

Endpoint ini untuk mendapatkan list group tembusan

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name    | Type   | Description                                |
| ------- | ------ | ------------------------------------------ |
| `limit` | number | Limitasi per halaman                       |
| `page`  | number | Filter untuk menuju halaman ke-n           |
| name    | string | Filter untuk mencari berdasarkan nama grup |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    groups: [
      {
        id: <int>,
        group_name: <string>,
        group_description: <string>,
        is_active: <int>,
        users: [
          {
            id: <int>,
            name: <string>,
            nip: <string>,
            organization: {
              id: <int>,
              organization_name: <string>,
            },
            role: {
              id: <int>,
              role_name: <string>,
            },
          }
        ],
        user_create: {
          id: <int>,
          name: <string>,
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
