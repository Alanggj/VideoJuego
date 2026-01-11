# La Venganza Del Dios Del Amor (Videojuego)

## Descripción
**La Venganza Del Dios Del Amor** es un videojuego de plataformas 2D desarrollado con el motor gráfico **Phaser JS**. El juego presenta una experiencia interactiva donde los jugadores controlan personajes (Nano/Shizuka) para recolectar objetos, evitar enemigos y progresar a través de niveles, todo ejecutado en el navegador web.

## Arquitectura
El proyecto utiliza una estructura de videojuego basada en escenas gestionada por el motor **Phaser**:
```
VideoJuego/
├── public/
│   ├── index.html        # Contenedor del Canvas
│   ├── script/           # Lógica del Juego (Phaser)
│   │   ├── gameScene.js  # Escena Principal (Gameplay)
│   │   ├── menu.js       # Menú Principal
│   │   └── ...           # Otras escenas y utilidades
│   ├── assets/           # Recursos (Sprites, Audio, Fondos)
│   └── css/              # Estilos de la UI externa al Canvas
├── server.js             # Servidor estático (Node.js/Express)
└── package.json          # Dependencias
```
*   **Motor de Juego (Cliente)**: **Phaser 3.x** maneja el bucle de juego, física (Arcade Physics), renderizado y entrada del usuario.
*   **Servidor**: Una pequeña capa de **Node.js con Express** sirve los archivos estáticos a los clientes.

## Tecnologías Utilizadas
*   **Phaser JS**: Motor gráfico para la lógica y renderizado del juego.
*   **JavaScript (ES6+)**: Lenguaje principal.
*   **HTML5 / CSS3**: Estructura y estilos del contenedor.
*   **Node.js + Express**: Servidor web ligero (backend estático).
*   **LocalStorage**: Persistencia de datos en el navegador.

## Características
*   **Múltiples Personajes**: Selección entre Nano y Shizuka con sprites y sonidos únicos.
*   **Sistema de Juego**:
    *   Física de plataformas clásica (saltar, correr).
    *   Sistema de Vidas y Puntuación.
    *   Enemigos con IA simple y proyectiles (Bombas).
    *   Items Especiales (Bonus, Inmunidad).
*   **Gestión de Audio**: Música de fondo y efectos de sonido dinámicos.
*   **Estados de Juego**: Menú, Tutorial, Gameplay, Pausa, Game Over (con animación Canvas).

## Instalación y Ejecución
1.  **Requisitos**: Node.js instalado.
2.  **Instalar Dependencias**:
    ```bash
    npm install
    ```
3.  **Ejecutar Servidor**:
    ```bash
    node server.js
    ```
4.  **Jugar**: Abrir `http://localhost:3000` en el navegador.

## Modelo de Datos
*   **Persistencia Local (`localStorage`)**:
    *   `playerName`: Nombre del jugador.
    *   `gameVolume`: Configuración de volumen.
    *   `vidasActuales`: Persistencia de vidas entre niveles.
*   **Estado en Memoria (Tiempo de Ejecución)**:
    *   Clases `GameScene`, `Jugador` gestionan el estado activo (posición, score, enemigos) dentro del ciclo de vida de Phaser.

## Autor
**Alan Gael Gallardo Jimenez**
