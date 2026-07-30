# haskelar.pl

Statyczna strona **AlwaysInTouch** hostowana na GitHub Pages.

Warstwa jest celowo niezależna od serwera Proxmox: polityka prywatności musi być
osiągalna także wtedy, gdy własna infrastruktura jest wyłączona. Google Play
weryfikuje ten adres i wymaga, żeby działał.

## Adresy

| URL | Zawartość |
|---|---|
| `https://haskelar.pl/polityka-prywatnosci/` | polityka prywatności (PL) |
| `https://haskelar.pl/privacy/` | privacy policy (EN) |

Adres do wklejenia w Play Console: **`https://haskelar.pl/privacy/`**
(wersja EN, z `hreflang` prowadzącym do polskiej).

## Struktura

| Ścieżka | Rola |
|---|---|
| `index.html` | strona główna |
| `polityka-prywatnosci/index.html` | polityka prywatności PL |
| `privacy/index.html` | privacy policy EN |
| `404.html` | strona błędu |
| `style.css` | wspólne style |
| `CNAME` | domena własna GitHub Pages |

## Źródło treści

Źródłem prawdy dla treści polityki jest `apps/OfflineTravelHub/docs/PRIVACY.md`
w repozytorium aplikacji. **Każda zmiana zachowania aplikacji musi trafić najpierw
tam, potem na obie wersje językowe tej strony.** Rozjazd między polityką
a zachowaniem aplikacji jest naruszeniem zasad Google Play.

## Podział ruchu

- `haskelar.pl`, `www` → **GitHub Pages** (ten kod)
- pozostałe subdomeny → **Cloudflare Tunnel** → serwer Proxmox
