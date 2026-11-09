# ART MEDITERRANI

## Flujo obligatorio de revisión y publicación

El repositorio activo es `davidruizgarci/artmediterrani-web`. La web estática se sirve desde `public/` mediante el Worker `artmediterrani-web` de Cloudflare Workers Builds. La rama de producción es `main`.

1. Confirma el remoto y la rama de producción antes de escribir o subir cambios. Crea una rama de trabajo desde el último `origin/main`. Mantén los commits acotados y revisa el diff antes del push. El repositorio es público. Incluye solo código y recursos autorizados para publicación. Excluye credenciales, archivos privados, historiales locales y recursos sin uso.
2. Sube solo la rama de trabajo al repositorio activo. Cloudflare Workers Builds ejecuta `npx wrangler preview` para esa rama. La configuración de Wrangler apunta a `./public` en `assets.directory` e incluye el bloque `previews`. Usa la URL real del panel o del registro de Cloudflare.
3. Verifica que el build de Preview terminó correctamente y corresponde al último commit remoto de la rama. Abre la URL y comprueba por HTTP las páginas y los recursos modificados. Prueba escritorio y móvil en los idiomas afectados. Si falla el build, corrige en la rama o informa del bloqueo. Si cambia el commit, vuelve a verificar.
4. Entrega a David el enlace verificado y el SHA antes de abrir una PR. Incluye ambos en la descripción de la PR hacia `main`. Para correcciones en una PR existente, vuelve a compartir el enlace y el SHA verificados.
5. David debe aprobar la PR y autorizar expresamente la publicación. La aprobación y la autorización de publicación son decisiones separadas. Una fusión en `main` puede activar el despliegue automático de producción. Quedan prohibidos los pushes directos a `main`, la fusión, el auto-merge, los despliegues directos a producción y los cambios de configuración de producción sin autorización explícita de David.
6. Antes de fusionar, comprueba el SHA aprobado, los checks, el diff final y si `main` ha avanzado. Si el cambio afecta a Wrangler o al despliegue, revisa además el comando de producción, el Worker de destino y el directorio de archivos. Después de una fusión autorizada, verifica el despliegue y la web pública. Si falla, informa del estado y prepara la recuperación para que David autorice ejecutarla.

Consulta [PREVIEW_PROCESS.md](PREVIEW_PROCESS.md) para los pasos de Cloudflare y las comprobaciones antes y después de publicar.
