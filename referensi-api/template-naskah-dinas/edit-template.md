# Edit Template

<mark style="color:green;">`PUT`</mark>`/manuscipt-templates/{id}`

Endpoint untuk edit template naskah dinas

**Headers**

| Name          | Value                 |
| ------------- | --------------------- |
| Content-Type  | `multipart/form-data` |
| Authorization | `Bearer <token>`      |

**Body**

| Name                            | Type   | Description                         | Validation                                               | Catatan                                                                                                                              |
| ------------------------------- | ------ | ----------------------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| manuscript\_type\_id            | number | Jenis naskah                        | required\|number\|exists:manuscript\_types.id            |                                                                                                                                      |
| manuscript\_characterisrtic\_id | number | Sifat naskah                        | required\|number\|exists:manuscript\_characterisrtics.id |                                                                                                                                      |
| organization\_unit\_id          | number | Pemilik naskah/naskah dikelola oleh | required\|number\|exists:organization\_units.id          | Berdasarkan permission. kalau dikasih akses untuk ada pemilihan maka ambil dari inputan. kalau tidak ada, ambil dari user yang login |
| template\_code                  | string | Kode template                       | required\|string\|max:100\|unique                        |                                                                                                                                      |
| template\_name                  | string | Nama template                       | required\|string\|max:255                                |                                                                                                                                      |
| template\_file                  | file   | File hasil template                 | required\|file\|max:50MB\|mimes:docx,pdf                 |                                                                                                                                      |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  status: true,
  status_code: 200,
  message: "Berhasil mengedit template naskah!",
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
