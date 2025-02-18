Instalación del Repositorio
  Para clonar el repositorio en tu máquina local, ejecuta el siguiente comando en tu terminal:
  git clone https://github.com/AsGuizar/Login-Register.git
  cd Login-Register

Instalación de Dependencias
  Antes de ejecutar la API, instala las dependencias necesarias utilizando npm:
  npm install

Ejecución de la API
  Para iniciar el servidor backend, ejecuta:
  node server/server.js

Funcionamiento del Proyecto
  Backend
  El backend está basado en Node.js y gestiona las operaciones de autenticación mediante un servidor Express. Se encarga de:
  •	Registrar nuevos usuarios y almacenarlos en users.json.
  •	Manejar el inicio de sesión verificando credenciales con hashing seguro.
  •	Implementar medidas de seguridad como salt para fortalecer la seguridad de las contraseñas.
  •	Limitar intentos de inicio de sesión para prevenir ataques de fuerza bruta.
  •	Servir archivos estáticos para el frontend.

Hashing y Seguridad de Contraseñas
  El sistema utiliza crypto para proteger las contraseñas:
  1.	Se genera un salt aleatorio para cada usuario.
  2.	La contraseña se convierte en un hash usando HMAC-SHA256 con el salt.
  3.	Al autenticar, el hash de la entrada del usuario se compara con el hash almacenado.

Frontend
  El frontend es una aplicación simple basada en HTML, CSS y JavaScript que interactúa con el backend a través de peticiones HTTP. Se encarga de:
  •	Enviar datos de registro e inicio de sesión al backend.
  •	Manejar respuestas y mostrar mensajes al usuario.
  •	Redirigir al usuario a una página de bienvenida tras un inicio de sesión exitoso.

Flujo de Autenticación
  1.	Registro:
  o	El usuario ingresa su nombre de usuario y contraseña.
  o	El sistema genera un salt, calcula el hash y lo almacena.
  o	Se muestra un mensaje de confirmación.
  2.	Inicio de Sesión:
  o	El usuario ingresa sus credenciales.
  o	El sistema calcula el hash y lo compara con el almacenado.
  o	Si es correcto, redirige a la página de bienvenida.
  o	Si falla varias veces, bloquea temporalmente el acceso.
