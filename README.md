# nol.auth

Authentification et autorisation en pur [Nolc](https://noliae-nolc.s3.gra.io.cloud.ovh.net/nolc-latest-linux-x86_64.tar.gz), sans dépendance lourde.

> **État : fondation (v0.1).** Les primitives ci-dessous sont implémentées et testées. La feuille de route liste la suite. Construit lot par lot, chaque étape avec CI verte.

## Installation

```toml
[dependances]
"nol-auth" = { git = "https://github.com/Noliae-France/nol-auth" }
```

## Licence

MIT © 2026 Bastien LANGUEDOC.

## Livré (v0.2)
- **JWT HS256** : `jwt_signe(payload, cle)`, `jwt_verifie(jeton, cle)`, `jwt_charge(jeton)` — HMAC-SHA256 **réel** (vendorisé de la stdlib crypto), comparaison à **temps constant**.
- **Sessions signées** : `session_signe(valeur, cle)`, `session_verifie(signe, cle)`.
- Base64URL, Bearer (`bearer_extrait`), RBAC (`rbac_autorise`).

```nol
let jeton = jwt_signe("{\"sub\":\"42\"}", cle)
jwt_verifie(jeton, cle)     // true ; un jeton forgé avec une autre clé -> false
```

## Feuille de route
- Sessions signées, cookies sûrs (SameSite/HttpOnly/Secure), rotation des clés
- **JWT** (HS256/RS256), **OAuth 2.0**, **OpenID Connect** ([spec](https://openid.net/specs/openid-connect-core-1_0.html))
- RBAC complet + permissions fines
