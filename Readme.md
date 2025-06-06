# Portainer Stack para Traefik by DigitalLFRAN

Este stack despliega Portainer CE (Community Edition) y lo configura automáticamente para ser gestionado y asegurado por un stack de Traefik existente.

## Requisitos del Dojo

-   **Un stack de Traefik funcional:** Debes tener un Traefik v3 corriendo, preferiblemente usando [el stack base de DigitalLFRAN](https://github.com/bicibikes15/Traefik).
-   **Una red Docker compartida:** Tu Traefik debe estar conectado a una red Docker externa.
-   **Un subdominio** para Portainer (ej. `portainer.tudominio.com`) apuntando a la IP de tu servidor Traefik.

## El Ritual de Invocación (Instalación)

**1. Clonar el Repositorio**

```bash
# Reemplaza 'tu-github' con tu nombre de usuario y 'tu-repo-portainer' con el nombre del repo
git clone [https://github.com/tu-github/tu-repo-portainer.git](https://github.com/tu-github/tu-repo-portainer.git)
cd tu-repo-portainer

2. Verificar la Red Externa Compartida

Este stack debe conectarse a la red de Traefik. El nombre estandarizado para todos los proyectos de DigitalLFRAN es digitallfran_net.

Si no la has creado con el stack de Traefik, créala ahora:

Bash

docker network create digitallfran_net

3. Configurar tu Dominio

Crea tu archivo de configuración local a partir de la plantilla. El archivo .env nunca debe hacerse público.

Bash

cp .env.example .env
Ahora, edita el archivo .env (nano .env) y establece tu dominio para Portainer:

PORTAINER_DOMAIN: El subdominio que has elegido para Portainer.

4. Desplegar a Portainer

Con tu archivo .env listo y el DNS apuntando correctamente, invoca el jutsu final.

Bash

docker compose up -d
Verificación
Traefik detectará automáticamente el nuevo contenedor, le asignará un certificado SSL y lo hará disponible en el dominio que configuraste. Visita https:// seguido de tu PORTAINER_DOMAIN. La primera vez, Portainer te pedirá que crees tu usuario administrador y contraseña.

---
Con esta pieza, el rompecabezas está completo.