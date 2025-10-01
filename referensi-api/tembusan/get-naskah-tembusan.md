# Get Naskah Tembusan

<mark style="color:green;">`GET`</mark> `/manuscripts-`passthroughs

Endpoint untuk list naskah yang tembusan nya sesuai dengan user yang sedang login. \
\
Untuk bagian user\_destination, hanya mengambil yang group\_id nya null saja begitu pula bagian user\_passtrough

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Query String**

| Name                              | Type   | Description                                          |
| --------------------------------- | ------ | ---------------------------------------------------- |
| `limit`                           | number | Limitasi per halaman                                 |
| `page`                            | number | Filter halaman ke-n                                  |
| organization\_id                  | number | Filter berdasarkan user unit kerja tujuan            |
| manuscript\_received\_start\_date | date   | Tanggal mulai masuk naskah                           |
| manuscript\_received\_end\_date   | date   | Tanggal akhir masuk naskah                           |
| manuscript\_characteristic\_id    | number | Filter berdasarkan sifat naskah                      |
| keyword                           | string | Filter bedasarkan nomor/pengirim/nama/perihal naskah |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    manuscripts: [
      {
        id: <int>,
        manuscript_number: <string>,
        manuscript_date: <date>,
        manuscript_received_date: <date>,
        manuscript_from: <string>,
        manuscript_description: <string>,
        count_user_destination: <int>,
        manuscript_characteristic: {
          id: <int>,
          name: <string>
        },
        
        is_proccessed_disposition: <int>,
        manuscript_file: <string>, // Path ke file
        created_at: <timestamp>,
        updated_at: <timestamp>
      }
    ],
    pagination: {
      current_page: <int>,
      limit: <int>,
      total_page: <int>,
      total_data: <int>,
    }
  }
}
```
{% endtab %}
{% endtabs %}
