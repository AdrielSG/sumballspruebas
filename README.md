# VictoriaManager - Mecánica de victoria en 2D

## Descripción
Este proyecto implementa una **mecánica de victoria simple** para un juego 2D en Unity.  
Cuando un jugador pierde (cae por debajo de un límite en Y), se muestra:

1. Una **imagen de victoria** (sprite) en el centro de la escena.  
2. El **prefab del jugador ganador** en su posición actual.

Esta implementación permite comprobar la inserción de **scripts y recursos** en Unity.

---

## Estructura de carpetas

Assets/
├── Resources/
│ ├── img/
│ │ └── victoria.png # Sprite de victoria
│ └── prefabs/
│ └── PrefabGanador.prefab # Prefab del jugador ganador
└── Scripts/
└── VictoriaManager.cs

---

## Configuración en Unity

1. **Preparar jugadores**  
   - Tener dos objetos `Transform` que representen a los jugadores (por ejemplo: `JugadorA` y `JugadorB`).  

2. **Agregar el script**  
   - Crear un `GameObject` vacío llamado `VictoriaManager`.  
   - Añadir el script `VictoriaManager.cs`.  
   - Asignar los jugadores en los campos `Jugador A` y `Jugador B`.  

3. **Preparar assets en Resources**  
   - Imagen de victoria: `Assets/Resources/img/victoria.png`  
   - Prefab del ganador: `Assets/Resources/prefabs/PrefabGanador.prefab`  

4. **Ejecutar la escena**  
   - Cuando un jugador caiga por debajo de `limiteDerrotaY`, se mostrará la imagen de victoria y se instanciará el prefab del ganador.

---

## Notas de implementación

- El script **no pausa el juego**; únicamente muestra la imagen y el prefab.  
- La imagen de victoria se muestra como un **Sprite 2D** con `SpriteRenderer`.  
- El prefab del ganador se instancia en la posición del jugador ganador.  
- Se utiliza `Resources.Load` para cargar dinámicamente los assets, por lo que deben estar en la carpeta `Resources`.

---

## Personalización

- `limiteDerrotaY`: Ajusta el valor de Y que determina cuándo un jugador pierde.  
- Orden de renderizado de la imagen: Ajusta `sr.sortingOrder` para que la imagen aparezca sobre otros objetos.  
- Posición de la imagen: Actualmente se instancia en `(0,0,0)`; puede modificarse según la escena.

---

**Resultado esperado:**  
Al ejecutarse la escena y un jugador caer por debajo del límite definido, se observará la **imagen de victoria** en pantalla y el **prefab del jugador ganador** en su posición, cumpliendo los requisitos de la práctica.
