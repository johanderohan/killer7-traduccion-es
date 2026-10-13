# killer7 — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Traducción al **español de España** de *killer7* (Nintendo GameCube, 2005), el thriller de Grasshopper
Manufacture y Suda51 publicado por Capcom, que nunca salió en español (la versión europea solo traía inglés,
francés y alemán).

La versión americana cuenta casi toda la historia con escenas habladas en inglés **sin subtítulos**: solo
subtitula unas pocas frases. Este parche traduce los textos del juego y además **añade subtítulos en
castellano** a las escenas y a los vídeos, para que la historia se entienda de principio a fin.

La traducción se reparte como **parche**: no incluye el juego. Necesitas tu propia copia para aplicarlo.

## Estado

Última versión: **[v1.0 — Primera versión](../../releases/tag/v1.0)**. Estado: **en revisión**.

| Parte | Estado |
|---|---|
| Subtítulos de las escenas | **Añadidos**: unos 760 subtítulos en 62 escenas, sincronizados con la voz |
| Subtítulos de los vídeos | **Añadidos**: unos 360 subtítulos en 20 vídeos |
| Diálogos de Iwazaru, Travis y los demás fantasmas | Traducidos (3.083 mensajes) |
| Mensajes de escenario, paneles, cartas de Emir y tutoriales | Traducidos |
| Menús, televisor de personalidades, opciones, tarjeta de memoria, mapa, títulos y objetivos de misión, rótulos de zona y letreros de los cruces | Traducidos (620 textos) |
| Texto dentro de imágenes (dificultad, tutorial de controles, Sí/No, menú de pausa, fichas de misión, pantallas de capítulo, concurso de carteles…) | **168 imágenes rehechas** |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « »** |
| Partida completa de principio a fin | **No realizada** |

El disco americano conserva la pista de subtítulos de la edición japonesa (que tenía las mismas voces en
inglés) y un reproductor de subtítulos que la versión USA dejó apagado. El parche lo activa y le da pistas
en castellano. Los subtítulos de las escenas que en la USA no tenían ninguno se han traducido desde **lo que
se oye en inglés** (transcrito automáticamente), con el guion japonés del disco como apoyo; el resto, desde
la versión americana. Traducción y revisión asistidas por IA, sin revisión humana independiente.

Fuera del texto, el parche hace tres cambios en el ejecutable: activa los subtítulos de las escenas y de los
vídeos, dibuja el contorno negro de los subtítulos de escena (en la versión USA no llegaba a pintarse y el
texto blanco no se leía sobre fondos claros) y pone la fecha de las partidas guardadas en formato
día/mes/año.

### Cómo se ha comprobado

Todo en emulador (Dolphin, núcleo libretro), no en una GameCube real:

- **Jugado desde partida nueva** en el disco 1: avisos de inicio, título, opciones, dificultad, la ficha de
  la misión, la escena inicial, el tutorial de controles completo, el capítulo «Angel» en el edificio Celtic
  hasta el combate con el Duplicator, con Iwazaru, los fantasmas, el mapa, el menú de pausa, el televisor de
  personalidades, los rótulos de zona y los letreros de los cruces. **Guardado y carga**: se ha guardado en la
  habitación de Harman, se ha reiniciado y se ha cargado la partida.
- **Escenas lanzadas directamente**: las 62 escenas con subtítulos de los dos discos (también las variantes de
  Hopper7) se han reproducido en el juego, con todos sus subtítulos revisados uno a uno y la sincronía medida
  frente a la voz grabada. Dos escenas muy pesadas no arrancan con este método y quedan sin ver.
- **Vídeos**: se han reproducido con subtítulos el vídeo inicial del disco 1 y el primero del disco 2; el texto
  de los demás se ha revisado fuera del juego.
- Una auditoría automática comprueba en cada imagen de disco los límites de memoria y de formato conocidos.
  Los parches se han aplicado sobre los originales y el resultado se ha comparado byte a byte.

### Limitaciones conocidas

- No se ha jugado de principio a fin: la mayor parte del juego se ha comprobado con escenas y pantallas
  lanzadas directamente o de forma estática.
- No se ha probado en una GameCube real ni el cambio de disco a mitad de partida.
- Se mantienen en inglés los logotipos y títulos de capítulo, los carteles del decorado, los nombres de las
  bebidas de la máquina (la pista del puzle depende de sus iniciales), los botones LOAD/SAVE y NEXT/END, y
  algunos objetos de los letreros de los cruces.
- Algunas frases del doblaje son muy breves y su subtítulo pasa rápido; en escenas largas el subtítulo puede
  llegar a ir hasta un segundo por detrás de la voz en el emulador.

## Cómo aplicar el parche

Hay **un parche por disco**. Aplica cada uno a su disco.

1. Descarga los dos parches `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia del juego en versión **USA**, como imágenes ISO (GCM) completas de los dos discos.
3. **Comprueba que tus discos son los correctos**:

   | | Disco 1 | Disco 2 |
   |---|---|---|
   | Archivo | `Killer 7 (USA) (Disc 1).iso` | `Killer 7 (USA) (Disc 2).iso` |
   | Tamaño | 1.459.978.240 bytes | 1.459.978.240 bytes |
   | MD5 | `4cdb132c4ab2d95b9095fdb1647e9636` | `58a84314ef4ccf17bd118a03009f93ad` |

   ```bash
   md5sum "Killer 7 (USA) (Disc 1).iso"                    # Linux
   md5 "Killer 7 (USA) (Disc 1).iso"                       # macOS
   CertUtil -hashfile "Killer 7 (USA) (Disc 1).iso" MD5    # Windows
   ```

   Si no coincide (por ejemplo, si tu copia está en RVZ, GCZ o CISO), conviértela antes a ISO completa con
   Dolphin y vuelve a comprobarla. Si sigue sin coincidir, el parche fallará o dará un resultado corrupto.
4. Aplica cada parche a su disco:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**:
     `xdelta3 -d -s "Killer 7 (USA) (Disc 1).iso" Killer7.ES.v1.0.Disco1.xdelta "Killer 7 (ES) (Disc 1).iso"`
     (y lo mismo con el disco 2 y su parche)
5. Para **v1.0**, los discos resultantes tienen el mismo tamaño y estos MD5:
   disco 1 **`f60a114b7400041de60b5d06e690c281`**, disco 2 **`6b2818d62aec47c6fb1ffb8cdf189afa`**.
6. Carga los discos traducidos en tu emulador (probado en Dolphin) o en tu cargador habitual.

Aplica cada versión sobre los **discos originales**, no sobre unos ya traducidos.

## Cambios

### v1.0 — 13 de octubre de 2026
- Primera versión: killer7 en castellano, con subtítulos en todas las escenas habladas y en los vídeos.
- Traducidos los diálogos de los fantasmas, mensajes, cartas, menús, mapa, misiones y rótulos en imagen.
- Tildes, eñes y signos de apertura en las fuentes del juego, con el mismo aspecto que las originales.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con Grasshopper
Manufacture, Capcom ni Nintendo. Aquí no se distribuye el juego ni ninguna parte de él: solo un parche que
modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
