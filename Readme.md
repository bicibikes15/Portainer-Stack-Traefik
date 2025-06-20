<div align="center">
  <img src="https://www.portainer.io/hubfs/portainer_icon_blue.svg" alt="Portainer Logo" width="120"/>
  <h1 align="center">Portainer Stack para Traefik by DigitAllFran</h1>
  <p>
    <img src="https://img.shields.io/badge/Portainer%20CE-2.20+-blue?style=for-the-badge&logo=portainer&logoColor=white" alt="Portainer CE"/>
    <img src="https://img.shields.io/badge/Traefik-v3-blueviolet?style=for-the-badge&logo=traefikproxy&logoColor=white" alt="Traefik v3"/>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
    <img src="https://img.shields.io/badge/Let's%20Encrypt-003A70?style=for-the-badge&logo=letsencrypt&logoColor=yellow" alt="Let's Encrypt"/>
  </p>
</div>

> [!NOTE]
> **Stack listo para producción**  
> Despliega Portainer CE y lo expone de forma segura detrás de Traefik, con SSL automático y gestión centralizada.

> [!TIP]
> **Requisitos previos**  
> - Stack de **Traefik v3** funcional (recomendado: [Traefik Stack by DigitAllFran](https://github.com/bicibikes15/Traefik))
> - **Red Docker externa** compartida (`digitallfran_net`)
> - **Subdominio** para Portainer (ej. `portainer.tudominio.com`) apuntando a la IP del servidor Traefik

> [!IMPORTANT]
> **El Ritual de Invocación (Instalación)**
> 1. **Clona el repositorio:**
>    ```
>    git clone https://github.com/bicibikes15/Portainer-Stack-Traefik.git
>    cd Portainer-Stack-Traefik
>    ```
> 2. **Verifica o crea la red externa compartida:**
>    ```
>    docker network create digitallfran_net
>    ```
> 3. **Configura tu dominio:**
>    ```
>    cp .env.example .env
>    # Edita el archivo .env y define PORTAINER_DOMAIN con tu subdominio
>    ```
> 4. **Despliega Portainer:**
>    ```
>    docker compose up -d
>    ```

> [!WARNING]
> **Verificación y primer acceso**  
> Traefik detectará el contenedor, generará el certificado SSL y expondrá Portainer en tu subdominio.  
> Accede a `https://<tu PORTAINER_DOMAIN>`.  
> La primera vez, Portainer te pedirá crear usuario y contraseña de administrador.

> [!NOTE]
> **¿Todo conectado?**  
> Si ves el panel de Portainer tras loguearte, ¡rompecabezas completo!  
> Ahora puedes gestionar todos tus stacks Docker desde una interfaz web segura.

---

