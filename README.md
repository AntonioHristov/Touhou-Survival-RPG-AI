# Touhou Survival RPG AI (TSRA)

<p>Un motor narrativo diseñado para ejecutar partidas de rol de supervivencia ambientadas en el mundo de Touhou Project. Este sistema permite gestionar estados complejos, mecánicas de mundo dinámicas y una sincronización precisa entre el usuario y una Inteligencia Artificial.</p>

## Herramientas Incluidas
### 1. Interfaz de Usuario (index.html)

Una consola visual para los jugadores que permite:

	Visualizar atributos de combate y supervivencia.
	Gestionar el inventario (recoger, soltar o mover objetos entre contenedores).
	Generar Multi-Prompts automáticos para evitar el límite de caracteres en la IA, manteniendo la integridad del mundo.

### 2. Sincronizador de Datos (syncJSON.html)

Herramienta crítica para fusionar la respuesta de la IA con la partida:

	Protección de Memorias: Evita que la IA sobrescriba o borre recuerdos previos del personaje.
	Gestión de Limbo: Si un objeto se pierde o es robado en la narrativa, se archiva automáticamente en un contenedor global.
	Auditoría de Reglas: Corrige automáticamente valores ilegales (ej. HP mayor al máximo) sugeridos por la IA.

## Cómo empezar

	Aprender la estructura JSON (opcional pero muy recomendado) ya que te ayudaría con bugs, partidas corruptas, etc. Si empiezas de 0 con JSON entra a la carpeta txt y echa un vistazo a introduccionJSON.txt
	Abre la Interfaz de Usuario (index.html) en un navegador (ej: Google Chrome, Mozilla Firefox, Opera, Safari, etc) y carga tu partida guardada en la carpeta "saves" (inicialmente "datosBase.json", luego la más reciente o la que quieras al exportar tu partida).
	Observa el contexto de tu partida y ve a la sección "Elegir Acción/Copiar Prompt" o ve abajo del todo en la sección "Ver Todo". Elige una acción de la lista o escribe una personalizada.
	Exporta tu partida en la carpeta "saves". Copia el prompt generado y pégalo en tu IA preferida (Ejemplos: Gemini, ChatGPT, etc).
	Copia la respuesta JSON de la IA y úsala en el Sincronizador (SyncJSON.html, se abre en un navegador también) para actualizar tu estado de partida. Arrastra el archivo o pega el código de tu JSON de partida en "JSON Base (Estructura Objeto)" y el JSON de la respuesta de la IA en "JSON Update (Cambios)". Haz click en sincronizar, observa los cambios sugeridos y personaliza según tu gusto (cambiando datos de JSON de la IA, etc y sincronizando de nuevo). Cuando apruebes los cambios exporta el archivo sincronizado en la carpeta "saves", ábrelo con la Interfaz de Usuario (index.html) y se repite el ciclo

## Recursos opcionales para mejorar la experiencia
**Un TTS (text to speach) con varias voces:**
Online gratuito: https://ttsmaker.com/es
Descargable: Balabolka https://www.cross-plus-a.com/es/balabolka.htm
**Música:**
Recomendado, la que más te guste (Si no tienes idea puedes probar con música de touhou project la misma franquicia del juego)

## Características del Motor

	Gestión de Dificultad Dinámica: Tres niveles (Easy, Normal, Hard) que afectan las probabilidades de victoria y la hostilidad del entorno. (Por ahora es solo un prototipo así que solo hay dificultad fácil y no es personalizable a no ser que cambies el JSON desde código. Planeado interfaz personalizable en futuras versiones)
    Formato de Tiempo: 24h (60 min = 1h).
	Muerte: Permadeath activa cuando hp <= 0.
	Omnipotencia: Soporte para modo narrativo "Dios" mediante el flag omnipotent: true.
	Mecánicas de Supervivencia: Sistema de decaimiento por hora de comida, agua, sueño y regeneración de HP/Energía.
	Efectos Ambientales: Simulación de las toxinas del Bosque Mágico (Magic Forest Spores) con estados de inmunidad y alucinaciones.
	Sistema de Inventario Avanzado: Soporte para contenedores (mochilas, cofres) con IDs de objetos únicos y reutilizables.
	Persistencia de Datos: Exportación e importación mediante archivos .json para mantener la continuidad de la historia.
    Más detalles en txt -> gdd.txt