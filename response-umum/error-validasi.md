---
description: >-
  Berikut adalah format response jika terdapat kesalahan dalam validasi input
  dari client side. Didalam property data, ada array yang berisi nama inputan
  dan pesan error nya.
---

# Error Validasi

```
{
  code: 400,
  status: false,
  message: <string>,
  data: [
    {
      field: <string>,
      message: <string>
    }
  ],
}
```
