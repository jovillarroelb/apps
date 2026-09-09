# Recursos de marca — SMERA

## Archivos

- `logo-mark.svg` — ícono/símbolo oficial, azul petróleo + cobre, para fondos claros.
- `logo-mark-white.svg` — mismo ícono en blanco + cobre, para fondos oscuros.
- `logo-full.svg` — lockup completo oficial: ícono + wordmark "SMERA" +
  descriptor (texto vectorizado, color azul petróleo fijo — pensado para
  uso sobre fondos claros).
- `logo-full-white.svg` — lockup completo oficial blanco para fondos oscuros.

Estos son los archivos **oficiales** provistos por el equipo SMERA
(reemplazaron una reconstrucción provisional usada durante el desarrollo).

## Uso en la aplicación

El ícono y el wordmark se consumen en la app vía `components/brand/Logo.tsx`,
que expone:

- `<LogoMark tone="navy" | "white" />` — solo el ícono, renderiza
  `<img src="/brand/logo-mark(-white).svg">`.
- `<Logo tone="dark" | "light" />` — lockup oficial completo en SVG,
  seleccionando la versión para fondo claro u oscuro.

Los lockups completos sí se referencian en la UI para evitar reconstrucciones
manuales del wordmark.

## Paleta

```
--smera-navy:   #113A51
--smera-copper: #AC7542
--smera-white:  #FFFFFF
```

## Dónde se usa el logo en la app

- `components/layout/Header.tsx` — logo compacto (ícono + wordmark), tono dark
- `components/layout/Footer.tsx` — logo compacto, tono light
- `components/layout/PortalSidebar.tsx` / `AdminSidebar.tsx` — logo compacto, tono light
- `app/(auth)/layout.tsx` — logo compacto, tono light (panel navy) y dark (mobile)
