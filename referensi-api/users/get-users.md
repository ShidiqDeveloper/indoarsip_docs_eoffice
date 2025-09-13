# Get Users

<mark style="color:green;">`GET`</mark>`/users`

Endpoint ini untuk mendapatkan list users disertai dengan pagination

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name                   | Type   | Description                            |
| ---------------------- | ------ | -------------------------------------- |
| `limit`                | string | Filter limitasi per halaman            |
| `page`                 | number | Filter untuk menuju halaman ke-n       |
| organization\_unit\_id | number | Filter berdasarkan unit kerja          |
| role\_id               | number | Filter berdasarkan jabatan             |
| keyword                | string | Filter user berdasarkan nama/nip/email |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    users: [
      {
        id: <int>,
        name: <string>,
        nip: <string>,
        email: <string>,
        phone: <int>,
        last_login: <timestamp>,
        photo: <string>,
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
