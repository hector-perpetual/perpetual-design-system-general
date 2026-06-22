# Perpetual Design System

Fuente de verdad del sistema de diseño de **Perpetual Technologies**, empaquetada como skill de Claude. Define tokens de color, tipografía ArminGrotesk, logos (color y fondo oscuro), espaciado, componentes y reglas de marca, de forma agnóstica al formato.

Las skills de salida (`perpetual-html-design`, `perpetual-pptx-design`) consumen estos tokens. Cuando un valor de marca cambia, se edita aquí una vez y se propaga a todos los formatos.

## Contenido

```
perpetual-design-system/
├── SKILL.md                      # Tokens + índice (fuente de verdad)
├── assets/
│   ├── logo/
│   │   ├── perpetual-color.svg   # Fondos claros
│   │   └── perpetual-dark.svg    # Fondos oscuros (blanco + naranja/amarillo)
│   └── fonts/                    # ArminGrotesk, 5 pesos (base64)
└── references/
    ├── tokens.md                 # Tabla completa: CSS vars + RGB para Office
    ├── components.md             # Specs de componentes
    └── voice-and-rules.md        # Voz e idioma + reglas duras
dist/
└── perpetual-design-system.skill # Paquete listo para subir a Claude.ai
```

## Instalación

### Claude.ai / app (Pro, Max, Team, Enterprise)

1. Descarga `dist/perpetual-design-system.skill`.
2. Settings → Capabilities → Skills → subir el `.skill`.
3. Requiere Code Execution / File Creation activado.
4. Team/Enterprise: un Owner puede provisionarla para toda la organización.

### Claude Code

```bash
git clone https://github.com/hector-perpetual/perpetual-design-system-general.git
cp -r perpetual-design-system-general/perpetual-design-system ~/.claude/skills/
```

La skill queda disponible la próxima vez que abras Claude Code.

## Uso

No genera archivos por sí sola: provee el lenguaje de marca. Se combina con una skill de formato (HTML, PPTX, DOCX) para producir el deliverable. Se activa de forma automática cuando alguien del equipo pide generar un reporte, dashboard, propuesta, presentación o cualquier asset de marca.

## Versionado

Cambios de marca (color, logo, tipografía, reglas) se hacen en `SKILL.md` y `references/tokens.md`, se versiona con un tag semántico (`v1.0.0`, `v1.1.0`...) y se re-empaqueta el `.skill`.

## Licencia

Uso interno de Perpetual Technologies. Todos los derechos reservados.
