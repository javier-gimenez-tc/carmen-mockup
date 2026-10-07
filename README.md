# C.A.R.M.E.N. - Mockup estatico

Mockup navegable de la solucion propuesta por QUENTAL para Navantia.
Contiene pantallas HTML, estilos e imagenes; no requiere backend, dependencias
ni compilacion. Los datos y las acciones son de demostracion; el acceso
corporativo mostrado no implementa autenticacion real.

## Vista local

Abrir `index.html` directamente en un navegador. La portada permite acceder
a los recorridos de Compras y Demandante.

## Publicar en GitHub Pages

El repositorio local utiliza la rama `main`. Para subirlo por primera vez:

1. Crear un repositorio vacio en GitHub, sin README, licencia ni gitignore.
2. Desde esta carpeta, ejecutar los comandos siguientes, sustituyendo la URL
   por la del repositorio creado:

```sh
git add .
git commit -m "Prepare static mockup for GitHub Pages"
git remote add origin https://github.com/OWNER/REPOSITORY.git
```

3. En GitHub, abrir **Settings > Pages > Build and deployment** y seleccionar
   **GitHub Actions** como **Source**. Si no aparece Pages, comprobar los
   permisos, el plan y las politicas de la organizacion.
4. Ejecutar `git push -u origin main`.
5. Consultar **Actions > Deploy static mockup to GitHub Pages**. Al terminar,
   la URL estara disponible en el despliegue y en **Settings > Pages**.

La URL habitual para un repositorio de proyecto es:

```text
https://OWNER.github.io/REPOSITORY/
```

Cada push a `main` actualiza el sitio. Tambien se puede ejecutar el workflow
manualmente desde **Actions > Deploy static mockup to GitHub Pages > Run workflow**.
Si el primer despliegue fallo antes de activar Pages, volver a ejecutarlo.

## Estructura y mantenimiento

- `index.html`: portada y mapa de pantallas.
- `*.html`: pantallas y recorridos del mockup.
- `assets/css/`: estilos compartidos.
- `assets/img/`: recursos de imagen.
- `.github/workflows/pages.yml`: despliegue mediante las acciones oficiales de Pages.
- `.nojekyll`: desactiva el procesamiento de Jekyll.

El workflow publica unicamente los HTML de la raiz, `assets/` y `.nojekyll`.
No publica la documentacion ni la configuracion del repositorio. Mantener
las rutas de enlaces y recursos relativas, sin una barra inicial, para que
funcionen bajo `/REPOSITORY/`. Respetar mayusculas y minusculas en las rutas.
La tipografia se carga desde Google Fonts y necesita conexion a Internet.

## Visibilidad

GitHub Pages no utiliza el login simulado del mockup como control de acceso.
El sitio puede ser publico incluso si el repositorio es privado, segun el
plan y la configuracion de GitHub. Confirmar la autorizacion para publicar
el contenido antes del primer push; no incluir credenciales ni datos reales.