# nol.auth

Authentification et autorisation en pur [Nolc](https://github.com/Noliae-France/nolc), sans dépendance lourde.

> **État : fondation (v0.1).** Les primitives ci-dessous sont implémentées et testées. La feuille de route liste la suite. Construit lot par lot, chaque étape avec CI verte.

## Installation

```toml
[dependances]
"nol-auth" = { git = "https://github.com/Noliae-France/nol-auth" }
```

## Licence

MIT © 2026 Bastien LANGUEDOC.

## Livré (v0.1)
`bearer_extrait` (Authorization: Bearer), `rbac_autorise` (RBAC minimal, rôle admin).

## Feuille de route
- Sessions signées, cookies sûrs (SameSite/HttpOnly/Secure), rotation des clés
- **JWT** (HS256/RS256), **OAuth 2.0**, **OpenID Connect** ([spec](https://openid.net/specs/openid-connect-core-1_0.html))
- RBAC complet + permissions fines
