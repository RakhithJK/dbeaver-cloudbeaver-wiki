You can open the SQL Editor with an existing connection via an external link.

All you need is to know one of these parameters:

Parameter|Description|URL example
---|---|---
id|Connection ID|http://{serverURL}/open?id=postgres-jdbc-00000000000-00000000000000000
name|Connection name|http://{serverURL}/open?name=RandomName@localhost
url|Connection URL|http://{serverURL}/open?url=jdbc:postgresql://localhost:5432/randomdb

To find these parameters open the connection Info in the Metadata Editor.

![Снимок экрана 2022-05-23 102153](https://user-images.githubusercontent.com/59531286/169770641-fab48a25-c3ac-4e56-b5aa-e89900d45bbe.png)

![Снимок экрана 2022-05-23 102531](https://user-images.githubusercontent.com/59531286/169769224-6af43b11-be18-4037-a145-6ab6b0255779.png)

