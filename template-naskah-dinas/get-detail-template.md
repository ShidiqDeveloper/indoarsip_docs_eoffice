# Get Detail Template

<mark style="color:green;">`GET`</mark>`/manuscipt-templates/{id}`

Endpoint untuk get detail template naskah dinas

**Headers**

| Name          | Value                 |
| ------------- | --------------------- |
| Content-Type  | `multipart/form-data` |
| Authorization | `Bearer <token>`      |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: "Ditemukan!",
  data: {
    template_code: <string>,
    template_name: <string>,
    template_file: <string>, // link url dokumen
    manuscript_type: {
      id: <int>,
      code: <string>,
      name: <string>,
    },
    manuscript_characterisrtic: {
      id: <int>,
      code: <string>,
    },
    organization_unit: {
      id: <int>,
      organization_code: <string>,
      organization_name: <string>,
    },
    created_at: <timestamp>,
    updated_at: <timestamp>
  }
}
```
{% endtab %}
{% endtabs %}
