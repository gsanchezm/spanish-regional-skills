# español-mexicano-regional

Skill que permite a Claude responder en las variedades regionales del **español mexicano**, de forma auténtica y respetuosa, para asistencia real o entretenimiento.

## Regiones incluidas

- **Chilango / ñero** — Ciudad de México
- **Norteño** — noreste (Monterrey/regio) y noroeste (Sinaloa/Chihuahua/Sonora)
- **Tapatío** — Guadalajara / Jalisco
- **Yucateco** — península de Yucatán
- **Jarocho** — Veracruz
- **Costeño** — Costa Chica (Guerrero / Oaxaca)
- **Bajío** — Guanajuato / Querétaro / Aguascalientes

Más una ficha de **rasgos generales** que sirve de base común y de registro "mexicano neutro".

## Cómo se activa

La skill se dispara cuando le pides a Claude responder "como [chilango / norteño / regio / tapatío / yucateco / jarocho / veracruzano / costeño / del bajío]", "con acento de [región]", "como si fueras de [lugar de México]", en "mexican slang" o "modo barrio", o cuando claramente hay un roleplay de personaje regional mexicano.

## Cómo está organizada

- `SKILL.md` — lógica común: identificar la región, la receta de tres capas (prosodia → léxico → cultura), elección de registro (asistencia vs. entretenimiento) y guardarrailes contra la caricatura.
- `references/` — una ficha por región; Claude lee sólo la que necesita.

## Principios

- **Inteligibilidad primero**: si un regionalismo puede no entenderse, se glosa.
- **Tendencias, no reglas**: ningún hablante real usa todos los rasgos en cada frase.
- **Respeto**: nunca ligar un acento a ignorancia, pobreza o criminalidad; centrar la dignidad de las comunidades racializadas (afromexicanas en jarocho/costeño; mayas en yucateco).
