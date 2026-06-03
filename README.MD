
# 🏎️ Universal Motorsport Timing
*Ecosistema de telemetría de alta frecuencia (Web) y gestión de calendario F1 (Android)*


### Índice
- [🏎️ Universal Motorsport Timing](#️-universal-motorsport-timing)
    - [Índice](#índice)
    - [1. Personas del Proyecto](#1-personas-del-proyecto)
    - [2. Descripción del Proyecto](#2-descripción-del-proyecto)
      - [Plataforma Web: Live Timing](#plataforma-web-live-timing)
      - [App Android: Universal Motorsport Timing Calendar (UMTC)](#app-android-universal-motorsport-timing-calendar-umtc)
      - [Capturas de pantalla](#capturas-de-pantalla)
      - [Stack tecnológico](#stack-tecnológico)
    - [3. Aportación por Módulos](#3-aportación-por-módulos)
    - [4. Repositorios de Código](#4-repositorios-de-código)
    - [5. Artefactos en Producción](#5-artefactos-en-producción)
    - [6. Documentación e Infraestructura](#6-documentación-e-infraestructura)
    - [7. Gestión del Proyecto (Jira)](#7-gestión-del-proyecto-jira)
    - [8. Documentación de Código (Compodoc)](#8-documentación-de-código-compodoc)

---

### 1. Personas del Proyecto
| Nombre completo | Rol en el proyecto |
| ------ | ------ |
| **Guillermo Diáñez Gómez** | Desarrollador Fullstack / Arquitecto de Android & Telemetría |

---

### 2. Descripción del Proyecto
**Universal Motorsport Timing** es una solución integral para aficionados a la Fórmula 1 que combina el procesamiento de datos en tiempo real con una herramienta de gestión de temporada móvil.

#### Plataforma Web: Live Timing
Un dashboard interactivo de "segunda pantalla" que procesa streams en vivo de alta frecuencia de F1. 
*   **Tabla de Tiempos Interactiva:** Clasificación en vivo con intervalos (Gap/Interval) e historiales de neumáticos (stints).
*   **Mapa del Circuito Dinámico:** Canvas interactivo que posiciona monoplazas mediante coordenadas bidimensionales (X, Y) y algoritmos de interpolación.
*   **Comunicaciones por Radio:** Reproducción de audios de transmisiones entre pilotos y boxes en tiempo real.

#### App Android: Universal Motorsport Timing Calendar (UMTC)
Aplicación nativa construida con tecnologías modernas para el seguimiento del calendario de F1.
*   **Pantallas Principales:** Lista de carreras, detalle expandido con cronograma de sesiones (timeline visual) e inicio de sesión.
*   **Funcionalidades Avanzadas:** 
    *   **Gestión de Zonas Horarias:** Conversión automática de horas UTC a la hora local del dispositivo.
    *   **Integración de Clima:** Previsiones meteorológicas en tiempo real para cada sesión mediante la API de Open-Meteo.
    *   **Sistema de Banderas Dinámico:** Carga de banderas desde CDN para optimizar el tamaño del APK.
    *   **Multimedia:** Uso de CameraX para capturar fotos de carreras y acceso a la galería mediante MediaStore.

#### Capturas de pantalla

<p align="center">
  <img src="./sources/img/image.png" alt="Plataforma Web - Live Timing" width="580" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="./sources/img/captura_movil.jpeg" alt="App Android - UMTC Calendar" width="200" />
</p>



#### Stack tecnológico
| Capa | Tecnología |
| ------ | ------ |
| **Frontend Web** | Angular 17+, RxJS, Signals, Angular Material |
| **App Móvil** | Kotlin, Jetpack Compose, Material Design 3, Hilt, Room, Coroutines |
| **Backend / Proxy** | Node.js, Express, WebSockets, Pako (descompresión binaria) |
| **APIs & Servicios** | F1 SignalR, Open-Meteo, Cloudinary, Retrofit & Gson |

---

### 3. Aportación por Módulos
*(Apartado obligatorio según la guía normativa)*

| Módulo | Profesor/a | Aportación en Universal Motorsport |
| :--- | :--- | :--- |
| **Acceso a datos** | Juan Antonio García Gómez | Persistencia local en Android mediante **Room Database** y gestión de perfiles con **Cloudinary** para avatares. |
| **Programación multimedia y dispositivos móviles** | David Hormigo Ramírez | Implementación de **CameraX** y **MediaStore** en Android, y sistema de reproducción de **Team Radios** en la web. |
| **Programación de servicios y procesos** | David Hormigo Ramírez | Consumo de APIs REST con **Retrofit** y gestión de flujos reactivos con **StateFlow**. Descompresión binaria en tiempo real (Pako). |
| **Desarrollo de interfaces** | Carmen Campos Fernández | UI declarativa con **Jetpack Compose** y **Material Design 3**. Uso de **OnPush** en Angular para alto rendimiento (60 FPS). |
| **Servidores y APIs** | Juan Antonio García Gómez | Creación del **Broker de Telemetría** en Node.js para negociar con servidores SignalR y eludir restricciones de CORS. |
| **Sistemas de gestión empresarial.** | Miguel Ángel Ronda Carracao | Sincronización de calendarios oficiales de la temporada 2026 y gestión de cronogramas de sesiones. |

---

### 4. Repositorios de Código
| Repositorio | Descripción | Enlace |
| ------ | ------ | ------ |
| **Web Frontend** | Aplicación Angular de Telemetría | [Enlace al Repo] |
| **Android App (UMTC)** | Aplicación Nativa Kotlin/Compose | [Enlace al Repo Android] |
| **Telemetry Broker** | Servidor Proxy de Datos | [Enlace al Repo Backend] |

---

### 5. Artefactos en Producción
| Artefacto | URL / Acceso |
| ------ | ------ |
| **Aplicación Web** | [URL de Despliegue (Ej: Railway/Vercel)] |
| **App Android (APK)** | [Enlace a descarga de APK en Releases] |
| **Credenciales** | **User:** test@example.com / **Pass:** 12345678 (mín. 8 caracteres) |

---

### 6. Documentación e Infraestructura
*   **Arquitectura:** Sigue principios de **Clean Architecture** y **MVVM** en la parte móvil (UI, Domain, Data layers).
*   **PDF Unificado:** [Enlace ](./sources/docs/merged.pdf) 

---

### 7. Gestión del Proyecto (Jira)
La planificación se ha gestionado mediante **Jira**, organizando el trabajo en **Epics**, tareas y estados de backlog.
*   [Enlace al PDF de Resumen Jira] (Incluye estadísticas y tablero final).

---

### 8. Documentación de Código (Compodoc)
Toda la lógica de Angular y servicios está documentada siguiendo estándares profesionales.
*   **Servidor Compodoc:** [Compodoc](https://universal-motorsport-timing-ap1n.vercel.app/)

