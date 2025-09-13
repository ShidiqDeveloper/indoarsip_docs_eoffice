# Get User Status

<mark style="color:green;">`GET`</mark>`/user-statuses`

Endpoint ini untuk mendapatkan list status user

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
      user_status: <string>,
      created_at: <timestamp>,
      updated_at: <timestamp>,
    }
  ],
}
```
{% endtab %}
{% endtabs %}
