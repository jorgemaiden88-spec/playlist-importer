# Playlist Importer (PWA)

Pega una lista de canciones (una por línea) y crea la playlist en Spotify.
Para Apple Music busca cada canción y te da enlaces (sin cuenta Apple Developer no hay API de escritura).

## 1. Publicar (necesita HTTPS)
Spotify exige redirect URI con HTTPS. Opción gratis: GitHub Pages.

    git init && git add . && git commit -m "playlist importer"
    gh repo create playlist-importer --public --source=. --push
    gh api -X POST repos/:owner/playlist-importer/pages -f "source[branch]=main" -f "source[path]=/"

Tu URL quedará como https://TU_USUARIO.github.io/playlist-importer/

## 2. App en Spotify
1. https://developer.spotify.com/dashboard -> Create app.
2. Redirect URI: la que muestra la app (ej. https://TU_USUARIO.github.io/playlist-importer/), exacta, con la / final.
3. API: Web API. Copia el Client ID y pégalo en la app.
4. Nota: desde feb 2026 el modo desarrollo de la API requiere cuenta Spotify Premium.

## 3. Instalar
- iPhone/iPad: Safari -> Compartir -> Agregar a pantalla de inicio.
- Android: Chrome -> menú -> Instalar app.
- Mac: Chrome/Edge -> Instalar, o Safari -> Archivo -> Agregar al Dock.

## Notas
- Formato por línea: "Artista - Canción" (o invertido con el selector). Acepta numeración al inicio.
- Qobuz y Apple Music API quedan para una segunda fase.
