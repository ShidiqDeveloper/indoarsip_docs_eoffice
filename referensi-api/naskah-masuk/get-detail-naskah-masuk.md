# Get Detail Naskah Masuk

<mark style="color:green;">`GET`</mark> `/manuscripts-in/{id_manuscript}`

Endpoint untuk mendapatkan detail naskah

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
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    id: <int>,
    manuscript_number: <string>,
    manuscript_date: <date>,
    manuscript_received_date: <date>,
    manuscript_from: <string>,
    manuscript_description: <string>,
    group_destination: {
      id: <int>,
      group_name: <string>,
    },
    user_destinations: [
      {
        group_destination: {
          id: <int>,
          group_name: <string>,
        } / NULL,
        user: {
          id: <int>,
          name: <string>,
          nip: <string>,
          role: {
            id: <int>,
            role_name: <string>,
          },
          organization: {
            id: <id>,
            organization_name: <string>,
            short_name: <string>,
          }
        }
      }
    ],
    manuscript_type: {
      id: <int>,
      name: <string>
    },
    manuscript_characteristic: {
      id: <int>,
      name: <string>
    },
    classification_code: {
      id: <int>,
      name: <string>,
      code: <string>
    },
    is_proccessed_disposition: <int>,
    media_receive: <string>,
    manuscript_file: <string>, // Path ke file
    manuscript_attachment: <string|null>, // Path ke file
    group_passthrough: {
      id: <int>,
      group_name: <string>
    } / NULL,
    user_passthroughs: [
      {
        group_passthrough: {
          id: <int>,
          group_name: <string>
        } / NULL,
        user: {
          id: <int>,
          name: <string>,
          nip: <string>,
          role: {
            id: <int>,
            role_name: <string>,
          },
          organization: {
            id: <id>,
            organization_name: <string>,
            short_name: <string>,
          }
        }
      }
    ],
    user_dispositions: [
      {
        user: {
          id: <int>,
          name: <string>,
          nip: <string>,
          role: {
            id: <int>,
            role_name: <string>,
          },
          organization: {
            id: <id>,
            organization_name: <string>,
            short_name: <string>,
          }
        }
      }
    ] / NULL,
    note_internal: <string|null>,
    is_filed: <bool>,
    created_at: <timestamp>,
    updated_at: <timestamp>
  }
}
```
{% endtab %}
{% endtabs %}
