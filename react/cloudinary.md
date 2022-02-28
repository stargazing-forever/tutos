## subir images por api
[doc](https://cloudinary.com/documentation/image_upload_api_reference)
1. Configurar tu preset en cloudinary.

2. Petición POST a la api par subir images `api.cloudinary.com/v1_1/IDDETUCUENTA/upload`.
  
3. En postman, petición POST, en body agregar key `file` y configurarlo type file y `subir 
  la imagen como value`, ademas agregar key `upload_preset` y añadir en value `el preset de tu app creado`.
  ,formData.append('folder', 'journal-app') para carpetas.
