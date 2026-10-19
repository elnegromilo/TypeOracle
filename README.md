# TypeOracle

Aprende SQL y administración de Oracle escribiendo cada comando. Dos juegos de mecanografía, en español, que funcionan en el navegador sin instalar nada.

> Proyecto educativo, no afiliado a Oracle. Oracle es una marca registrada de Oracle Corporation.

## Los juegos

| Juego | Misiones | Qué enseña |
|---|---|---|
| **[TipeaSQL](tipeasql/)** | 33 en 8 zonas | `SELECT`, `WHERE`, `ORDER BY`, funciones de Oracle (`SYSDATE`, `DUAL`, `NVL`, `\|\|`, `TO_CHAR`, `FETCH FIRST`, `ROWNUM`), `GROUP BY`, `JOIN`, subconsultas, DML con `COMMIT` y DDL con `VARCHAR2` y `NUMBER`. |
| **[TipeaDBA](tipeadba/)** | 39 en 8 zonas | SQL*Plus, arranque en tres etapas (`NOMOUNT`, `MOUNT`, `OPEN`), PDB, tablespaces y datafiles, tempfiles, usuarios y cuotas, control files y redo logs. |

Jugar en línea (GitHub Pages): https://elnegromilo.github.io/TypeOracle/

## Cómo se juega

- Cada misión trae un enunciado y parte de la sentencia ya escrita. Tú tecleas el resto.
- Las mayúsculas y minúsculas no importan, salvo dentro de comillas.
- Cada letra correcta se pinta con colores de sintaxis y cada error se marca en rojo hasta que lo borres.
- Ganas hasta 3 estrellas según tus errores (usar la pista limita a 2), sumas XP y subes de rango.
- Al terminar ves la salida del comando, qué hace cada parte y una nota sobre lo propio de Oracle.
- En TipeaDBA, un panel muestra la instancia en vivo: etapa de arranque, contenedor de tu sesión, PDB, tablespaces, control files y redo logs. Se actualiza con cada comando que completas.

## Ejecutar en local

Cada juego es un solo archivo HTML sin dependencias. Descarga el repositorio y abre `index.html` en un navegador. Solo necesita internet para cargar las tipografías de Google Fonts; sin conexión usa tipografías del sistema.

```
TypeOracle/
├── index.html        menú de los juegos
├── tipeasql/
│   └── index.html
└── tipeadba/
    └── index.html
```

## Cómo añadir misiones

Las misiones están en el arreglo `LEVELS` de cada `index.html`. Cada una es una llamada a `lv(...)` con título, enunciado, sentencia, pista, explicación, nota de Oracle y, en TipeaDBA, el efecto sobre la instancia y la salida. El signo `§` separa lo que ya viene escrito de lo que el jugador debe teclear:

```js
`SELECT last_name, salary FROM employees §WHERE salary > 6000;`
```

## Notas

- **No es un motor SQL real.** El juego comprueba que escribas el comando de la misión y muestra una salida calculada sobre datos de ejemplo. En TipeaDBA el estado de la instancia es una simulación.
- Rutas y versión de los ejemplos de TipeaDBA: Oracle 19c, CDB `ORCLCDB`, archivos en `/u01/oradata/ORCLCDB/`.
- El progreso se guarda en `localStorage`, por navegador y por juego.

## Proyectos relacionados

Estos proyectos existen y cubren partes distintas. Hasta donde alcanzó la búsqueda, no encontré uno que una mecanografía de comandos, Oracle y administración de la base.

- [Oracle SQL Quest](https://github.com/Patricia-RJ/Juego-Oracle-): app gratuita en español para aprender SQL de Oracle con quizzes, retos y simulacros de examen.
- [Oracle Dev Gym](https://devgym.oracle.com/pls/apex/dg/competition/sql): quizzes y competiciones de SQL de Oracle, con modalidades de completar palabras clave.
- [SQL Syntax Blaster](https://codecanyon.net/item/sql-syntax-blaster-html5-coding-game/64391849): juego arcade de SQL en el que escribes la sintaxis (de pago).
- [Oracle Practice Hub](https://github.com/amirulyusoffstudy-droid/oracle-practice-hub): preguntas tipo test para el examen Oracle Database Administration I.

## Licencia

[MIT](LICENSE).
