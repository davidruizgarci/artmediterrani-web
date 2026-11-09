# Revisión y publicación de ART MEDITERRANI

El código está en [GitHub](https://github.com/davidruizgarci/artmediterrani-web). Cloudflare Workers Builds despliega el Worker `artmediterrani-web` desde `public/`. `main` es la rama de producción.

## Vista previa antes de la PR

1. Revisa el diff con `origin/main`, comprueba los recursos y sube la rama de trabajo.
2. En GitHub, abre los checks del último commit. Abre el resultado de **Workers Builds** y comprueba que el build de Cloudflare es de tipo Preview, que coincide con la rama y el SHA y que ha terminado correctamente.
3. Obtén el enlace de **Previews** en el Worker o del registro del build. El enlace al panel de compilación sirve para ver el estado y los registros. Comparte con David la URL de la web de vista previa.
4. Abre esa URL y verifica la navegación, los recursos modificados y el diseño en escritorio y móvil. Si el alias apunta a otra revisión, usa la URL específica de ese despliegue o espera a que se actualice y comprueba de nuevo.
5. Pasa a David la URL y el SHA verificados. Luego abre la PR hacia `main` con ambos datos. Si cambia la rama, repite las comprobaciones antes de pedir que se revise de nuevo.

## Publicación autorizada

- Revisa que la PR contiene el cambio acordado y que su último commit es el revisado. Si hay que actualizar la rama con cambios de `main`, genera una nueva vista previa y vuelve a compartirla.
- Si el diff incluye `wrangler.jsonc`, comprueba la compatibilidad con el comando de producción configurado y que sigue sirviendo `public/` desde el Worker previsto. Conserva la referencia al despliegue activo anterior.
- Una vez que David apruebe la PR y autorice la publicación, fusiona mediante GitHub. Una PR con varios commits relacionados puede fusionarse con **Squash and merge** si está habilitado y conviene registrar el conjunto como un cambio.
- Comprueba que Cloudflare despliega el commit resultante en `main` y que ese despliegue está activo. Verifica el dominio público, las páginas y los recursos afectados. Si el build falla o la comprobación detecta un problema, informa del estado y prepara una reversión del cambio o una recuperación del despliegue anterior, según corresponda, para autorización de David.

[Builds por rama de Cloudflare Workers](https://developers.cloudflare.com/workers/ci-cd/builds/build-branches/) · [Configuración de Previews](https://developers.cloudflare.com/workers/previews/configuration/)
