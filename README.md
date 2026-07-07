# firma-email — Mirai Tech

Imágenes públicas de las **firmas de correo** de Mirai. Alojadas aquí para que los clientes de
correo (Gmail, Apple Mail, etc.) puedan cargarlas por URL. Repo **público** a propósito: las
imágenes deben ser accesibles sin login para que se vean en los correos.

> El **código** que genera las firmas vive en el workspace de Mirai:
> `mirai/posicionamiento-de-marca/firma-email/` (ver su `README.md`). Este repo es solo el **hosting**.

## Estructura

```
firma-email/
├── comun/          # assets IGUALES para todos (no cambian por persona)
│   ├── wordmark.png   · logo "mirai"
│   ├── bar.png        · barra separadora de 7 franjas
│   ├── in-name.png    · LinkedIn (junto al nombre)
│   └── in/ig/yt/x/fb.png · íconos de redes de la empresa
└── empleados/      # 1 carpeta por persona, con SU foto de perfil
    └── gelier/
        └── avatar.png
```

## Cómo agregar la firma de un empleado nuevo

1. En el generador (`mirai/posicionamiento-de-marca/firma-email/build.py`): poner la foto en
   `avatar.jpg`, editar los datos (nombre, rol, correo, teléfono, LinkedIn) y el slug `EMP`.
2. `python3 build.py && bash render-assets.sh` → genera `assets/avatar.png` y el `gmail-firma.html`.
3. Subir la foto a este repo: `empleados/<slug>/avatar.png` (los assets de `comun/` ya están; no se
   tocan salvo cambio de marca).
4. Entregar al empleado su `gmail-firma.html` para copiar/pegar en Gmail.

Las URLs quedan:
`https://raw.githubusercontent.com/miraitechai/firma-email/main/empleados/<slug>/avatar.png`
