# Menambahkan Naskah

<mark style="color:green;">`POST`</mark> `/manuscripts-in`

Endpoint untuk menambahkan naskah masuk

**Headers**

| Name          | Value                 |
| ------------- | --------------------- |
| Content-Type  | `multipart/form-data` |
| Authorization | `Bearer <token>`      |

**Body**

```
{
  manuscript_number: <string>,
  manuscript_date: <date>,
  manuscript_received_date: <date>,
  manuscript_from: <string>,
  manuscript_description: <string>,
  group_destination_id: <int|null>,
  user_destinations: <array> [<int>, <int>, ...],
  manuscript_type_id: <int>,
  manuscript_characteristic_id: <int>,
  classification_code_id: <int>,
  media_receive: <string>,
  manuscript_file: <file>,
  manuscript_attachment: <file|null>,
  group_passthrough_id: <int|null>,
  user_passthroughs: <array> [<int>, <int>, ...],
  user_dispositions: <array> [<int>, <int>, ...],
  note_internal: <string|null>,
  is_filed: <bool>,
}
```

| Name                           | Type   | Description                 | Validation                                                                 |
| ------------------------------ | ------ | --------------------------- | -------------------------------------------------------------------------- |
| manuscript\_number             | string | Nomor Surat                 | required\|string\|max:255                                                  |
| manuscript\_date               | date   | Tanggal Surat               | required\|string\|date\_format:Y-m-d                                       |
| manuscript\_date               | date   | Tanggal Penerimaan Surat    | required\|string\|date\_format:Y-m-d                                       |
| manuscript\_from               | string | Pengirim Surat              | required\|string\|max:255                                                  |
| manuscript\_description        | string | Perihal Surat               | required\|string\|max:300                                                  |
| group\_destination\_id         | number | Grup Tujuan                 | nullable\|number\|exists:group\_destinations,id                            |
| user\_destinations             | array  | User tujuan                 | required\|array\|exists:users,id                                           |
| manuscript\_type\_id           | number | Bentuk Naskah               | required\|number\|exists:manuscript\_types,id                              |
| manuscript\_characteristic\_id | number | Sifat naskah                | required\|number\|exists:required\|number\|exists:manuscript\_types,id     |
| classification\_code\_id       | number | Kode klasifikasi naskah     | required\|number\|exists:required\|number\|exists:classification\_codes,id |
| media\_receive                 | string | Media penerimaan            | required\|string\|max:50                                                   |
| manuscript\_file               | file   | File naskah                 | required\|file\|max:50MB\|mime:docx,pdf,xlsx,xls                           |
| manuscript\_attachment         | file   | File lampira                | nullable\|file\|max:50MB\|mime:docx,pdf,xlsx,xls                           |
| group\_passthrough\_id         | number | Grup tembusan               | nullable\|number\|exists:group\_passthroughs,id                            |
| user\_passthroughs             | array  | User tembusan               | nullable\|array\|exists:users,id                                           |
| user\_dispositions             | array  | User disposisi              | nullable\|array\|exists:users,id                                           |
| note\_internal                 | string | Catatan Internal            | nullable\|string\|max:300                                                  |
| is\_filed                      | bool   | Parameter diberkaskan/tidak | required\|bool                                                             |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan naskah masuk!",
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
