# Get Data

Response untuk get data secara umum&#x20;

```
{
  code: 200,
  status: true,
  message: "Ditemukan!",
  data: {
    <attribute_data>: [
      {
        <data>
      }
    ],
    pagination: {
      current_page: <int>,
      per_page: <int>,
      total_page: <int>,
      total_data: <int>,
    }
  },
}
```
