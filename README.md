# Solucion:
1. Modificar el archivo **package.json** para agregar el comando **start**:
![image](https://user-images.githubusercontent.com/79205538/166124487-4de732a8-c6d3-4fcd-8f4c-52eff2d56e82.png)

2. Modificar el archivo **./node/Dockerfile** para agregar **RUN npm install** y el punto de entrada de la aplicación **CMD ["npm", "run", "start"]**
![image](https://user-images.githubusercontent.com/79205538/166124559-3786d7fd-96f8-4f50-861d-b77404c08d7b.png)

3. Renombrar el archivo **./node/env.example a env** para que pueda ser tomado en cuenta en el archivo **docker-compose.yaml**
![image](https://user-images.githubusercontent.com/79205538/166124607-4f2e01ed-50e9-4e68-b251-d6a155ee259c.png)

4. Modificar el archivo **./nginx/Dockerfile** para agregar el archivo de configuracion de nginx:
![image](https://user-images.githubusercontent.com/79205538/166124675-3569e4a0-a4f1-45b8-83a6-4eb53bf4059e.png)

5. Modificar el archivo **./nginx/nginx.conf** para que quede correctamente configurado:
![image](https://user-images.githubusercontent.com/79205538/166124700-06087ff0-e0e9-449b-9cc8-a66c0c37f80c.png)

6. En el archivo **./docker-compose.yaml** hacer los siguientes cambios:
- En la seccion **"app"** agregar las variables dockerfile y env_file
![image](https://user-images.githubusercontent.com/79205538/166124763-8c6b2cd7-2f36-4c65-9ed4-5b96619e7dac.png)
- En la seccion **db** agregar las variables dockerfile, ports y volumes
![image](https://user-images.githubusercontent.com/79205538/166124795-e9569ef2-9b06-4f7f-9df9-82d9f2fd4a14.png)
- En la seccion **nginx** agregar la variable dockerfile
![image](https://user-images.githubusercontent.com/79205538/166124815-1d3e6842-a07c-4b65-8acf-f0177630ca0e.png)
- Adicionalmente agregar las secciones volumes y networks
![image](https://user-images.githubusercontent.com/79205538/166124834-6e61ad9e-2788-4bb1-8025-0f354acdcc10.png)

Una vez estén listos los pasos anteriores, ejecutar en el directorio raiz los comandos:
- docker-compose build
- docker-compose up -d

y una vez se hayan iniciado los contenedores, ir a la dirección **http://localhost:3000** para visualizar la aplicación, refrescar la página varias veces para que se agreguen nombres:

![image](https://user-images.githubusercontent.com/79205538/166124941-43439092-85e0-4a4b-84ff-3e593544125b.png)
