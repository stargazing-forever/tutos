# GIT

## Para cambiar de usuario de una maquina windows
1. cambiar el `user.name` y el `user.email`:
    ```
      git config --global user.name "your-name"
      git config --global user.email "your-email"
    ```
3. Borrar las credenciales en `credential manager`.
4. Iniciar sesion en github en el navegador por default.
5. Empezar a usar git.

## Remover git de un proyecto
* para eliminar el tracking de git de un proyecto
    ```
        cd carpeta/
        rm -rf .git
    ```
## Remover el seguimiento de un archivo
   ```
      git rm .env --cached
   ```
