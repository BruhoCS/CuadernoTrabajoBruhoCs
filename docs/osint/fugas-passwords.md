# Fugas y contraseñas

Comprobar si una cuenta aparece en **filtraciones de datos** y buscar credenciales expuestas.

!!! warning "Límite ético"
    El objetivo en los ejercicios es **verificar la exposición**, no descargar ficheros de contraseñas ni **usar** ninguna credencial. Verificar sí; usar, no.

---

## Have I Been Pwned

> **Tipo:** Web · **Estado:** ✅ Usada (UD1-3, Ejercicio OSINT)

[haveibeenpwned.com](https://haveibeenpwned.com) — la referencia. De un correo dice **sí/no** y en **qué brechas** apareció (con fecha y qué datos se filtraron). **No** muestra la contraseña.

---

## LeakCheck

> **Tipo:** Web · **Estado:** ✅ Usada (Ejercicio OSINT)

[leakcheck.io](https://leakcheck.io) — de un correo muestra las **fuentes/brechas** y **contraseñas parciales** (`reme****`). El texto completo requiere plan de pago. Útil para confirmar exposición.

---

## DeHashed

> **Tipo:** Web · **Estado:** ✅ Usada (Ejercicio OSINT)

[dehashed.com](https://dehashed.com) — la que **sí** muestra la contraseña en claro de las filtraciones, pero el detalle es **de pago**. La búsqueda gratis solo indica el nº de incidentes.

---

## Intelligence X (IntelX)

> **Tipo:** Web · **Estado:** ✅ Usada (UD1-3, Ejercicio OSINT)

[intelx.io](https://intelx.io) — indexa **pastes, leaks y dark web**. Busca por correo o **dominio** y muestra en qué volcados de credenciales aparece (`mailpass`, `EmailPass`…). El contenido en claro queda tras **PRO**. El **Phonebook** ([phonebook.cz](https://phonebook.cz)) lista los correos de un dominio sin contraseñas.

---

## h8mail

> **Tipo:** CLI · **Estado:** ✅ Usada (UD1-3)

Busca correos en fugas e informa de cuentas comprometidas. Viene en Kali. Usa APIs de terceros (Hunter, HIBP…) configuradas en su `.ini`.

```bash
h8mail --gen-config               # crea h8mail_config.ini
h8mail -t correos.txt -c h8mail_config.ini
```

!!! note
    Si las keys del `.ini` están **comentadas** (con `;`), h8mail no consulta las bases → un "Not Compromised" puede ser falso negativo. Mejor contrastar con HIBP.

---

## Mozilla Monitor

> **Tipo:** Web · **Estado:** ⬜ Por probar

[monitor.mozilla.org](https://monitor.mozilla.org) — usa los datos de HIBP con una interfaz más amable.
