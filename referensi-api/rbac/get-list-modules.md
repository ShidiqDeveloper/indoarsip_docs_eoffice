# Get List Modules

<mark style="color:green;">`GET`</mark> `/roles/{id_role}/modules`

Endpoint ini untuk mendapatkan semua modules beserta pengecekan hak akses suatu module

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name        | Type   | Description                                              |
| ----------- | ------ | -------------------------------------------------------- |
| `parent_id` | number | Filter untuk mendapatkan module dari suatu parent module |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: false,
  message: "Ditemukan!",
  data: [
    {
      id: <int>,
      module_name: <string>,
      module_description: <string>,
      childs: [
        {
          id: <int>,
          module_name: <string>,
          module_description: <string>,
          created_at: <timestamp>,
          updated_at: <timestamp>,
          granted: <bool>
        }
      ]
    }
  ],
}
```
{% endtab %}
{% endtabs %}
