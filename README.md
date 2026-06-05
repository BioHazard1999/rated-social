# rated-social — sitio legal

Sitio estático (GitHub Pages) con la **Política de Privacidad** y los **Términos de
Servicio** de Rated, en 5 idiomas (ES/EN/FR/IT/DE), servido en https://rated-social.com.

- `/privacy` → política de privacidad
- `/terms` → términos de servicio

## Fuente y regeneración

El contenido se genera a partir de los `.md` canónicos del repo de la app
(`legal/*.md`). **No edites el HTML a mano**: edita los `.md` y regenera con:

```bash
node scripts/build-legal-site.mjs   # (desde el repo de la app)
```

Eso reescribe `index.html`, `privacy/index.html` y `terms/index.html`.

## Despliegue (una vez)

1. Crea el repo **público** `rated-social` y sube estos archivos.
2. GitHub → Settings → **Pages** → Source: *Deploy from a branch*, branch `main`, carpeta `/ (root)`.
3. En **Pages → Custom domain** escribe `rated-social.com` (el archivo `CNAME` ya lo fija) y marca **Enforce HTTPS**.
4. **DNS** en tu registrador del dominio:
   - 4 registros **A** del apex `rated-social.com` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (opcional) **CNAME** `www` → `<tu-usuario>.github.io`
5. Espera la propagación DNS (minutos–horas) y que Pages emita el certificado HTTPS.
6. En **App Store Connect** pon la Privacy Policy URL: `https://rated-social.com/privacy`.
