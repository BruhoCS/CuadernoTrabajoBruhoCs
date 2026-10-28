# Correos, usuarios y personas

De un **correo** o un **nombre de usuario** llegar a las cuentas, perfiles y a la persona.

---

## Hunter.io

> **Tipo:** Web / API · **Estado:** ✅ Usada (UD1-3, vía theHarvester y h8mail)

Busca **correos corporativos** de un dominio y su patrón (`nombre.apellido@`). Plan gratis con cuota mensual limitada. Su **API key** se configura en theHarvester (`~/.theHarvester/api-keys.yaml`, sección `hunter`) y en h8mail.

---

## Fingerprint.to

> **Tipo:** Web · **Estado:** ✅ Usada (Ejercicio OSINT)

De un **correo, usuario o teléfono** localiza **perfiles públicos** en más de 700 plataformas. Devuelve nombre real, usernames, ubicaciones, fotos y los perfiles (GitHub, Instagram, VK…). Limitada por tokens en el plan gratis.

Es la más cómoda para el pivote **email → perfiles → ubicación**.

---

## Holehe

> **Tipo:** CLI · **Estado:** ⬜ Por probar

Dice en qué **webs/servicios está registrado** un correo (sin alertar al objetivo).

```bash
pipx install holehe
holehe correo@gmail.com
```

---

## Epieos

> **Tipo:** Web · **Estado:** ⬜ Por probar

[epieos.com](https://epieos.com) — de un email (sobre todo **Gmail**) saca info de la cuenta Google asociada y servicios donde está registrado. Sin instalar nada.

---

## GHunt

> **Tipo:** CLI · **Estado:** ⬜ Por probar

Especializada en **cuentas Google/Gmail**: nombre, foto/ID, reseñas de Maps, YouTube… Requiere configurar cookies de Google.

```bash
pipx install ghunt
ghunt email correo@gmail.com
```

---

## WhatsMyName

> **Tipo:** Web / CLI · **Estado:** ⬜ Por probar

Buscador de **nombres de usuario**: comprueba en qué webs existe un handle. Web: [whatsmyname.app](https://whatsmyname.app).

---

## Sherlock

> **Tipo:** CLI · **Estado:** ⬜ Por probar

Busca un **username** en cientos de redes sociales.

```bash
pipx install sherlock-project
sherlock usuario
```

---

## Maigret

> **Tipo:** CLI · **Estado:** ⬜ Por probar

Como Sherlock pero con **más fuentes** y genera informe. Puede partir de username.

```bash
pipx install maigret
maigret usuario
```
