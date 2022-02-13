# Bienvenidos a nuestra pagina

En este mostraremos toda la documentacion , pasos de como realizar una recopilacion de datos de diferentes redes sociales con sus respectivas tecnicas junto al almacenamiento en sistemas gestores de bases de datos que administran datos no Sql y Sql.

## Recoleccion de datos de Platzi

Se realizo la recoleccion de datos de platzi la cual es una plataforma de educación online efectiva, la cual ofrece mas de 700 cursos enfocados ingeniería y desarrollo de software, diseño y UX, ingles, marketing digital, emprendimiento y negocios y mucho mas.

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

### Recoleccion de datos de Twitter

#### Twitter a CouchDb

Para la recoleccion de datos de Twitter a CouchDb se lo realizo en jupyter notebook mediante script , por ello lo mas revelevante de tomar en consideracion es :

Importar las librerias necesarias, que en este caso fueron 3.

![This is an image](https://southcentralus1-mediap.svc.ms/transform/thumbnail?provider=spo&inputFormat=png&cs=fFNQTw&docid=https%3A%2F%2Fepnecuador-my.sharepoint.com%3A443%2F_api%2Fv2.0%2Fdrives%2Fb!YP5u9sklC0iywPgRepMQVOdg8BAkAQlLoHr_GSobHaPNJuBAAf_VQKAw4x81bXaz%2Fitems%2F01PVDBQA25YB2MHGJD5RDL3U3PXNXEBIDL%3Fversion%3DPublished&access_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdWQiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAvZXBuZWN1YWRvci1teS5zaGFyZXBvaW50LmNvbUA2ODJhNGU2YS1hNzdmLTQ5NTgtYTNhYy05ZTI2NmQxOGFhMzciLCJpc3MiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAiLCJuYmYiOiIxNjQ0Nzc1MjAwIiwiZXhwIjoiMTY0NDc5NjgwMCIsImVuZHBvaW50dXJsIjoiTWwyby9jRUxiSDVZQ0NNcy9JeVlTQjBNM1VnY0ZVVDZKZk5kd2hITUZBQT0iLCJlbmRwb2ludHVybExlbmd0aCI6IjEyMCIsImlzbG9vcGJhY2siOiJUcnVlIiwidmVyIjoiaGFzaGVkcHJvb2Z0b2tlbiIsInNpdGVpZCI6IlpqWTJaV1psTmpBdE1qVmpPUzAwT0RCaUxXSXlZekF0WmpneE1UZGhPVE14TURVMCIsInNpZ25pbl9zdGF0ZSI6IltcImttc2lcIl0iLCJuYW1laWQiOiIwIy5mfG1lbWJlcnNoaXB8bWF5ZXJsaS5tZW5kZXpAZXBuLmVkdS5lYyIsIm5paSI6Im1pY3Jvc29mdC5zaGFyZXBvaW50IiwiaXN1c2VyIjoidHJ1ZSIsImNhY2hla2V5IjoiMGguZnxtZW1iZXJzaGlwfDEwMDMyMDAwNzEyOGU5ZmNAbGl2ZS5jb20iLCJzZXNzaW9uaWQiOiI0ZDI5MzdlZC02MTQzLTQ0ZmItYTU4NS02NjhhMjgyZTE4ZDkiLCJ0dCI6IjAiLCJ1c2VQZXJzaXN0ZW50Q29va2llIjoiMyIsImlwYWRkciI6IjE1Ny4xMDAuMTcwLjExOCJ9.OFpoM24ycHBOMHdtcnlLUTBabEdhbDBJVWEyRFdydUpyUE5JU2tsNHlSbz0&cTag=%22c%3A%7BC374C05D-2399-46EC-BDD3-6FBB6E40A06B%7D%2C1%22&encodeFailures=1&width=1366&height=581&srcWidth=&srcHeight=)

Tener las API es decir las claves para poder tener acceso a los datos.
![This is an image](https://southcentralus1-mediap.svc.ms/transform/thumbnail?provider=spo&inputFormat=png&cs=fFNQTw&docid=https%3A%2F%2Fepnecuador-my.sharepoint.com%3A443%2F_api%2Fv2.0%2Fdrives%2Fb!YP5u9sklC0iywPgRepMQVOdg8BAkAQlLoHr_GSobHaPNJuBAAf_VQKAw4x81bXaz%2Fitems%2F01PVDBQAY3OV55YV3N6ZBJ6NHHD7JUXMRY%3Fversion%3DPublished&access_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdWQiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAvZXBuZWN1YWRvci1teS5zaGFyZXBvaW50LmNvbUA2ODJhNGU2YS1hNzdmLTQ5NTgtYTNhYy05ZTI2NmQxOGFhMzciLCJpc3MiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAiLCJuYmYiOiIxNjQ0Nzc1MjAwIiwiZXhwIjoiMTY0NDc5NjgwMCIsImVuZHBvaW50dXJsIjoiTWwyby9jRUxiSDVZQ0NNcy9JeVlTQjBNM1VnY0ZVVDZKZk5kd2hITUZBQT0iLCJlbmRwb2ludHVybExlbmd0aCI6IjEyMCIsImlzbG9vcGJhY2siOiJUcnVlIiwidmVyIjoiaGFzaGVkcHJvb2Z0b2tlbiIsInNpdGVpZCI6IlpqWTJaV1psTmpBdE1qVmpPUzAwT0RCaUxXSXlZekF0WmpneE1UZGhPVE14TURVMCIsInNpZ25pbl9zdGF0ZSI6IltcImttc2lcIl0iLCJuYW1laWQiOiIwIy5mfG1lbWJlcnNoaXB8bWF5ZXJsaS5tZW5kZXpAZXBuLmVkdS5lYyIsIm5paSI6Im1pY3Jvc29mdC5zaGFyZXBvaW50IiwiaXN1c2VyIjoidHJ1ZSIsImNhY2hla2V5IjoiMGguZnxtZW1iZXJzaGlwfDEwMDMyMDAwNzEyOGU5ZmNAbGl2ZS5jb20iLCJzZXNzaW9uaWQiOiI0ZDI5MzdlZC02MTQzLTQ0ZmItYTU4NS02NjhhMjgyZTE4ZDkiLCJ0dCI6IjAiLCJ1c2VQZXJzaXN0ZW50Q29va2llIjoiMyIsImlwYWRkciI6IjE1Ny4xMDAuMTcwLjExOCJ9.OFpoM24ycHBOMHdtcnlLUTBabEdhbDBJVWEyRFdydUpyUE5JU2tsNHlSbz0&cTag=%22c%3A%7BDC7B751B-6D57-42F6-9F34-E71FD34BB238%7D%2C1%22&encodeFailures=1&width=1366&height=581&srcWidth=&srcHeight=)

Realizar bien la clase para la extraccion de datos.
![This is an image](https://southcentralus1-mediap.svc.ms/transform/thumbnail?provider=spo&inputFormat=png&cs=fFNQTw&docid=https%3A%2F%2Fepnecuador-my.sharepoint.com%3A443%2F_api%2Fv2.0%2Fdrives%2Fb!YP5u9sklC0iywPgRepMQVOdg8BAkAQlLoHr_GSobHaPNJuBAAf_VQKAw4x81bXaz%2Fitems%2F01PVDBQA2ZFNLK2RRYQZCJGRRBAZDOBM5B%3Fversion%3DPublished&access_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdWQiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAvZXBuZWN1YWRvci1teS5zaGFyZXBvaW50LmNvbUA2ODJhNGU2YS1hNzdmLTQ5NTgtYTNhYy05ZTI2NmQxOGFhMzciLCJpc3MiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAiLCJuYmYiOiIxNjQ0Nzc1MjAwIiwiZXhwIjoiMTY0NDc5NjgwMCIsImVuZHBvaW50dXJsIjoiTWwyby9jRUxiSDVZQ0NNcy9JeVlTQjBNM1VnY0ZVVDZKZk5kd2hITUZBQT0iLCJlbmRwb2ludHVybExlbmd0aCI6IjEyMCIsImlzbG9vcGJhY2siOiJUcnVlIiwidmVyIjoiaGFzaGVkcHJvb2Z0b2tlbiIsInNpdGVpZCI6IlpqWTJaV1psTmpBdE1qVmpPUzAwT0RCaUxXSXlZekF0WmpneE1UZGhPVE14TURVMCIsInNpZ25pbl9zdGF0ZSI6IltcImttc2lcIl0iLCJuYW1laWQiOiIwIy5mfG1lbWJlcnNoaXB8bWF5ZXJsaS5tZW5kZXpAZXBuLmVkdS5lYyIsIm5paSI6Im1pY3Jvc29mdC5zaGFyZXBvaW50IiwiaXN1c2VyIjoidHJ1ZSIsImNhY2hla2V5IjoiMGguZnxtZW1iZXJzaGlwfDEwMDMyMDAwNzEyOGU5ZmNAbGl2ZS5jb20iLCJzZXNzaW9uaWQiOiI0ZDI5MzdlZC02MTQzLTQ0ZmItYTU4NS02NjhhMjgyZTE4ZDkiLCJ0dCI6IjAiLCJ1c2VQZXJzaXN0ZW50Q29va2llIjoiMyIsImlwYWRkciI6IjE1Ny4xMDAuMTcwLjExOCJ9.OFpoM24ycHBOMHdtcnlLUTBabEdhbDBJVWEyRFdydUpyUE5JU2tsNHlSbz0&cTag=%22c%3A%7BAD562B59-3846-4486-9346-210646E0B3A1%7D%2C1%22&encodeFailures=1&width=1366&height=581&srcWidth=&srcHeight=)

Verificar que se realizo la conexion localmente con las bases de datos.

![This is an image](https://southcentralus1-mediap.svc.ms/transform/thumbnail?provider=spo&inputFormat=png&cs=fFNQTw&docid=https%3A%2F%2Fepnecuador-my.sharepoint.com%3A443%2F_api%2Fv2.0%2Fdrives%2Fb!YP5u9sklC0iywPgRepMQVOdg8BAkAQlLoHr_GSobHaPNJuBAAf_VQKAw4x81bXaz%2Fitems%2F01PVDBQA77AYRX2MY4LBEJBJ5YWABMGSW6%3Fversion%3DPublished&access_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdWQiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAvZXBuZWN1YWRvci1teS5zaGFyZXBvaW50LmNvbUA2ODJhNGU2YS1hNzdmLTQ5NTgtYTNhYy05ZTI2NmQxOGFhMzciLCJpc3MiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAiLCJuYmYiOiIxNjQ0Nzc1MjAwIiwiZXhwIjoiMTY0NDc5NjgwMCIsImVuZHBvaW50dXJsIjoiTWwyby9jRUxiSDVZQ0NNcy9JeVlTQjBNM1VnY0ZVVDZKZk5kd2hITUZBQT0iLCJlbmRwb2ludHVybExlbmd0aCI6IjEyMCIsImlzbG9vcGJhY2siOiJUcnVlIiwidmVyIjoiaGFzaGVkcHJvb2Z0b2tlbiIsInNpdGVpZCI6IlpqWTJaV1psTmpBdE1qVmpPUzAwT0RCaUxXSXlZekF0WmpneE1UZGhPVE14TURVMCIsInNpZ25pbl9zdGF0ZSI6IltcImttc2lcIl0iLCJuYW1laWQiOiIwIy5mfG1lbWJlcnNoaXB8bWF5ZXJsaS5tZW5kZXpAZXBuLmVkdS5lYyIsIm5paSI6Im1pY3Jvc29mdC5zaGFyZXBvaW50IiwiaXN1c2VyIjoidHJ1ZSIsImNhY2hla2V5IjoiMGguZnxtZW1iZXJzaGlwfDEwMDMyMDAwNzEyOGU5ZmNAbGl2ZS5jb20iLCJzZXNzaW9uaWQiOiI0ZDI5MzdlZC02MTQzLTQ0ZmItYTU4NS02NjhhMjgyZTE4ZDkiLCJ0dCI6IjAiLCJ1c2VQZXJzaXN0ZW50Q29va2llIjoiMyIsImlwYWRkciI6IjE1Ny4xMDAuMTcwLjExOCJ9.OFpoM24ycHBOMHdtcnlLUTBabEdhbDBJVWEyRFdydUpyUE5JU2tsNHlSbz0&cTag=%22c%3A%7B7D2306FF-1C33-4858-90A7-B8B002C34ADE%7D%2C1%22&encodeFailures=1&width=1366&height=581&srcWidth=&srcHeight=)

Colocar correctamente el nombre de usuario y contraseña que tengamos, crear la base de datos en la cual se va a guardar los datos.
![This is an image](blob:https://epnecuador-my.sharepoint.com/7250a6dc-9c16-4151-ab90-4eed906ab106)

![This is an image](blob:https://epnecuador-my.sharepoint.com/9273b810-87c8-43b9-b578-30c7dbddac4c)

Finalmente realizar el track con el parametro que se desea extraer los datos.
![This is an image](blob:https://epnecuador-my.sharepoint.com/c4e4ec20-5ac9-4cc0-8a6c-fb2103cd2c2f)

#### Twitter a MongoDb

### Recoleccion de datos de Facebook


### Recoleccion de datos de TikTok


### Recoleccion de datos de WebScraping


## Importacion y expotacion de datos.

Se realizo la importacion de los datos obtenidos mediante los diferentes gestores de bases de datos CouchDB,MongoDb,MongoDBAtlas y Mysql.

### Envio de datos de Couch a MongoDb

### Envio de datos de MongoDb a Couch  

### Envio de datos de Couch a MongoDbAtlas


### Envio de datos de MongoDbAtlas a Couch 

### Envio de datos de MongoDb a MySql

### Envio de datos de MySql  a MongoDb


### Envio de datos de MongoDbAtlas a Mysql.

### Envio de datos de Mysql a MongoDbAtlas.


Para más detalles, véase [El repositorio de GitHub](https://github.com/mayerli-mendez/Recoleccion_de_Datos.git).



##### Autores
- Manuel Auqui
- Leoni Guambo
- Mayerli Mendez
- Jorge Ortiz



