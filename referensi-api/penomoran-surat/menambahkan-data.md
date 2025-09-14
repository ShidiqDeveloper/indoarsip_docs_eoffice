# Menambahkan Data

## Create a new user

<mark style="color:green;">`POST`</mark> `/manuscript-number-formats`

Endpoint untuk menambahkan format nomor surat

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name                 | Type   | Description                                  | Validation                                    |
| -------------------- | ------ | -------------------------------------------- | --------------------------------------------- |
| manuscript\_type\_id | number | Jenis Naskah                                 | required\|number\|exists:manuscript\_types.id |
| number\_format       | string | Format nomor                                 | required\|string                              |
| number\_example      | string | Contoh Nomor                                 | required\|string                              |
| reset\_yearly        | number | Indikasi reset nomor tiap tahun. 1 yes, 0 no | required\|number\|enum(1,0)                   |
| is\_active           | number | Status format nomor                          | required\|number\|enum(1,0)                   |

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  code: 201,
  status: true,
  message: "Berhasil menambahkan format penomoran!",
  data: {
    id: <int>,
    number_format: <string>,
    number_example: <string>,
    reset_yearly: <int>,
    is_active: <int>,
    manuscript_type: {
      id: <int>,
      name: <string>,
    },
    created_at: <timestamp>,
    updated_at: <timestamp>,
  },
}
```
{% endtab %}
{% endtabs %}
