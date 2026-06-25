# Spanish Regional Skills

Skills para Claude que le permiten responder en las **variedades regionales del español**, de forma auténtica y respetuosa, tanto para asistencia real como para entretenimiento.

La idea es sencilla: el español no es un solo acento. Un chilango, un regio, un yucateco y un jarocho hablan distinto —en ritmo, en sonidos y en vocabulario— aunque compartan una base común. Estas skills le dan a Claude el material para adoptar cada voz como lo haría una persona de ese lugar, sin caer en caricatura ni en estereotipos ofensivos.

## Estado del proyecto

| País | Skill | Estado |
|------|-------|--------|
| 🇲🇽 México | `espanol-mexicano-regional` | ✅ Disponible |
| 🇦🇷 Argentina | `espanol-argentino-regional` | 🔜 Planeado |
| 🇨🇴 Colombia | `espanol-colombiano-regional` | 🔜 Planeado |
| ⋯ | resto de países hispanohablantes | 🔜 Planeado |

## Estructura del repositorio

```
spanish-regional-skills/
├── README.md
├── .gitignore
├── LICENSE
└── skills/
    └── espanol-mexicano-regional/
        ├── SKILL.md            # Lógica común: cómo elegir región, registro y guardarrailes
        └── references/         # Una ficha por variante (Claude lee sólo la que necesita)
            ├── general.md      # Base común del español mexicano
            ├── chilango.md     # CDMX (chilango / ñero)
            ├── norteno.md      # Norte (noreste y noroeste)
            ├── tapatio.md      # Guadalajara / Jalisco
            ├── yucateco.md     # Península de Yucatán
            ├── jarocho.md      # Veracruz
            ├── costeno.md      # Costa Chica (Guerrero / Oaxaca)
            └── bajio.md        # Guanajuato / Querétaro / Aguascalientes
```

Cada skill es independiente y vive en su propia carpeta dentro de `skills/`. Todas siguen el mismo patrón: un `SKILL.md` maestro con la lógica y los guardarrailes, más una carpeta `references/` con una ficha por región.

## Cómo funcionan estas skills

Cada skill se apoya en una **receta de tres capas** para sonar auténtica sin volverse parodia:

1. **Prosodia + ortografía** (lo que más trabajo hace): representar el ritmo y los sonidos de la región en la escritura.
2. **Unas pocas palabras emblemáticas** (3–6), usadas con naturalidad, no apiladas.
3. **Anclas culturales** (comida, música, lugares) para dar sabor.

Y un principio firme: **la inteligibilidad siempre gana**, y voicear una región nunca debe servir para burlarse de quien la habla. Cada `SKILL.md` incluye guardarrailes explícitos contra el clasismo y el racismo.

## Cómo instalar una skill

Las skills se distribuyen como archivos `.skill`. Para generar el paquete de una skill a partir de su carpeta, usa el empaquetador del *skill-creator* de Anthropic:

```bash
python -m scripts.package_skill skills/espanol-mexicano-regional
```

Eso produce `espanol-mexicano-regional.skill`, que puedes instalar en los productos de Claude que soporten skills. Consulta la documentación de Claude para los pasos de instalación según el producto.

## Cómo contribuir una nueva región o país

1. Copia la carpeta de una skill existente como plantilla.
2. Ajusta el `SKILL.md` (nombre, descripción de activación, selector de regiones).
3. Crea una ficha por región en `references/`, con prosodia, léxico, marcadores, anclas culturales y notas de registro/respeto.
4. Trata los rasgos como **tendencias, no reglas** (los hablantes reales mezclan registros constantemente).
5. Prioriza fuentes confiables; cuando el léxico de una región esté poco documentado, apóyate en prosodia y cultura antes que inventar.

## Nota sobre fuentes y respeto

El contenido lingüístico se apoya en dialectología académica del español (atlas lingüísticos, trabajos universitarios) y en glosarios culturales, contrastados para evitar errores y estereotipos. Las variedades regionales cargan identidad y, a veces, estigma real: estas skills buscan honrarlas, no reproducir prejuicios.

## Licencia

Ver [LICENSE](LICENSE).
