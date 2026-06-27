# Spanish Regional Skills

Skills para Claude que le permiten responder en las **variedades regionales del español**, de forma auténtica y respetuosa, tanto para asistencia real como para entretenimiento.

La idea es sencilla: el español no es un solo acento. Un chilango, un porteño, un paisa y un chapín hablan distinto —en ritmo, en sonidos y en vocabulario— aunque compartan una base común. Estas skills le dan a Claude el material para adoptar cada voz como lo haría una persona de ese lugar, sin caer en caricatura ni en estereotipos ofensivos.

## Estado del proyecto

| País | Skill | Regiones | Estado |
|------|-------|----------|--------|
| 🇲🇽 México | `espanol-mexicano-regional` | 7 | ✅ Disponible |
| 🇦🇷 Argentina | `espanol-argentino-regional` | 5 | ✅ Disponible |
| 🇧🇴 Bolivia | `espanol-boliviano-regional` | 3 | ✅ Disponible |
| 🇨🇱 Chile | `espanol-chileno-regional` | 3 | ✅ Disponible |
| 🇨🇴 Colombia | `espanol-colombiano-regional` | 6 | ✅ Disponible |
| 🇨🇷 Costa Rica | `espanol-costarricense-regional` | 3 | ✅ Disponible |
| 🇨🇺 Cuba | `espanol-cubano-regional` | 2 | ✅ Disponible |
| 🇪🇨 Ecuador | `espanol-ecuatoriano-regional` | 2 | ✅ Disponible |
| 🇸🇻 El Salvador | `espanol-salvadoreno-regional` | 2 | ✅ Disponible |
| 🇪🇸 España | `espanol-de-espana-regional` | 4 | ✅ Disponible |
| 🇬🇹 Guatemala | `espanol-guatemalteco-regional` | 3 | ✅ Disponible |
| 🇬🇶 Guinea Ecuatorial | `espanol-ecuatoguineano-regional` | 1+perfiles | ✅ Disponible |
| 🇭🇳 Honduras | `espanol-hondureno-regional` | 3 | ✅ Disponible |
| 🌎 resto | (orden alfabético) | — | 🔜 Planeado |

> El catálogo crece por tandas de 3 países en orden alfabético. Próxima tanda: Nicaragua, Panamá, Paraguay.

## Estructura del repositorio

```
spanish-regional-skills/
├── README.md
├── .gitignore
├── LICENSE
├── research/                            # Material de investigación (fuente de las skills)
│   ├── mexico.md
│   ├── argentina-bolivia-chile.md
│   ├── colombia-costarica-cuba.md
│   ├── ecuador-elsalvador-espana.md
│   └── guatemala-guineaecuatorial-honduras.md
└── skills/
    ├── espanol-mexicano-regional/        # chilango, norteno, tapatio, yucateco, jarocho, costeno, bajio
    ├── espanol-argentino-regional/       # rioplatense, cordobes, cuyano, noroeste, litoral
    ├── espanol-boliviano-regional/       # andino, camba, chapaco
    ├── espanol-chileno-regional/         # central, sur-chilote, norte
    ├── espanol-colombiano-regional/      # bogotano, paisa, costeno, valluno, pastuso, pacifico
    ├── espanol-costarricense-regional/   # central, guanacasteco, limonense
    ├── espanol-cubano-regional/          # habanero, oriental
    ├── espanol-ecuatoriano-regional/     # andino, costeno
    ├── espanol-salvadoreno-regional/     # nacional, oriental
    ├── espanol-de-espana-regional/       # castellano, andaluz, canario, bilingue
    ├── espanol-guatemalteco-regional/    # central, oriente, occidente
    ├── espanol-ecuatoguineano-regional/  # nacional + perfiles (fang, bubi, costa, annobones)
    └── espanol-hondureno-regional/       # central, norte, islas
```

Cada skill es independiente y vive en su propia carpeta dentro de `skills/`. Todas siguen el mismo patrón: un `SKILL.md` maestro con la lógica y los guardarrailes, más una carpeta `references/` con una ficha por región, y un `README.md` propio.

## Cómo funcionan estas skills

Cada skill se apoya en una **receta de tres capas** para sonar auténtica sin volverse parodia:

1. **Prosodia + ortografía (+ pronombre/tratamiento correcto)**: representar el ritmo, los sonidos y el sistema de tratamiento (tú/vos/usted/vosotros/ustedes) de la región.
2. **Unas pocas palabras emblemáticas** (3–6), usadas con naturalidad, no apiladas.
3. **Anclas culturales** (comida, música, lugares) para dar sabor.

Y un principio firme: **la inteligibilidad siempre gana**, y voicear una región nunca debe servir para burlarse de quien la habla. Cada `SKILL.md` incluye guardarrailes explícitos contra el clasismo, el racismo y los estereotipos regionales.

## Cómo instalar una skill

Las skills se distribuyen como archivos `.skill`. Para generar el paquete de una skill a partir de su carpeta, usa el empaquetador del *skill-creator* de Anthropic:

```bash
python -m scripts.package_skill skills/espanol-guatemalteco-regional
```

Eso produce `espanol-guatemalteco-regional.skill`, que puedes instalar en los productos de Claude que soporten skills. Consulta la documentación de Claude para los pasos de instalación según el producto.

## Cómo contribuir una nueva región o país

1. Copia la carpeta de una skill existente como plantilla.
2. Ajusta el `SKILL.md` (nombre, descripción de activación, selector de regiones).
3. Crea una ficha por región en `references/`, con prosodia, léxico, marcadores, sistema de tratamiento (tú/vos/usted/vosotros/ustedes), anclas culturales y notas de registro/respeto.
4. Trata los rasgos como **tendencias, no reglas** (los hablantes reales mezclan registros constantemente).
5. Prioriza fuentes confiables; cuando una variedad esté poco documentada, apóyate en prosodia y cultura antes que inventar.

## Nota sobre fuentes y respeto

El contenido lingüístico se apoya en dialectología académica del español (atlas lingüísticos como el ALEC del Instituto Caro y Cuervo, el ALPI peninsular o el Atlas Lingüístico-Etnográfico de Guatemala; trabajos universitarios; la obra de John Lipski sobre el español ecuatoguineano; academias de la lengua) y en glosarios culturales, contrastados para evitar errores y estereotipos. Las variedades regionales cargan identidad y, a veces, estigma real: estas skills buscan honrarlas, no reproducir prejuicios. La variedad de Guinea Ecuatorial, en particular, se trata con cuidado especial por ser la única africana y la menos documentada.

## Licencia

Ver [LICENSE](LICENSE).
