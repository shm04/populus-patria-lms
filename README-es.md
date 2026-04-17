# Populus Patria — Ecosistema EdTech

> **Categoría:** SaaS Empresarial / Marketplace Basado en Créditos  
> **Cliente:** Populus Patria / Elevate Agency  
> **Lead Architect:** Sebastian Hernandez ([Elevate Agency](https://your-elevate-link.com))  
> **Estado del Proyecto:** En Producción (v2.0)

---

## 🌎 Idiomas
Leer en [Inglés](./README.md)

---

# 📗 Tabla de Contenidos
- [📖 Acerca del Proyecto](#acerca-del-proyecto)
- [🚀 Características Clave y Economía Virtual](#caracteristicas-clave)
- [🏗️ Diseño Arquitectónico](#diseno-arquitectonico)
- [💻 Stack Tecnológico](#stack-tecnologico)
- [🧗 Profundidad Técnica: Sincronización Chronos & Ghost](#profundidad-tecnica)
- [🔒 Seguridad y Cumplimiento](#seguridad)
- [🔒 Política de Acceso al Código](#acceso-codigo)
- [👥 Autores](#autores)
- [📝 Licencia](#licencia)

---

## 📖 Acerca del Proyecto <a name="acerca-del-proyecto"></a>
Las escuelas de idiomas tradicionales luchan con la "Fragmentación de Herramientas": dependen de sistemas desconectados para pagos, programación, comunicación y aulas virtuales. 

Populus Patria resuelve esto proporcionando una Economía de Idiomas de grado empresarial unificada. Consolida todo el ciclo de vida del estudiante en un panel de alto rendimiento, eliminando los silos de datos y la fricción administrativa.

**Enlaces Clave:**
* [Live Demo / Sitio Web](https://app.populuspatria.com/) 
* [Recorrido de la Plataforma (Loom)](#)

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 🚀 Características Clave y Economía Virtual <a name="caracteristicas-clave"></a>
* **Ciclo Automatizado "Meet-to-Archive":** Un pipeline sofisticado que genera enlaces de Google Meet al reservar, detecta sesiones finalizadas vía Node-cron, extrae las grabaciones y las asigna automáticamente a los estudiantes correctos.
* **Grabaciones "Shadow" Inteligentes:** Sistema de control de acceso que asegura que los estudiantes solo vean grabaciones de clases ocurridas *después* de su fecha de inscripción, protegiendo la propiedad intelectual histórica.
* **Motor de Comunidad Híbrido:** Integración profunda con Rocket.Chat mediante SSO. Actúa como capa social y evita la fuga de negocio bloqueando el intercambio no autorizado de datos personales.
* **Sistema de Billetera Multimodal:** Economía virtual que soporta Stripe para transacciones globales en cinco modalidades distintas: CPP (Personalizado), CGG (Grupo General), CGP (Grupo Privado) y CCC (Club de Conversación).

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 🏗️ Diseño Arquitectónico <a name="diseno-arquitectonico"></a>
Construido utilizando un enfoque de **Diseño Basado en Dominio (DDD)** combinado con una Arquitectura de Capas para asegurar una alta mantenibilidad.

* **Módulos de Dominio:** El sistema se divide en dominios independientes que incluyen Auth, Pagos, Aulas y Comunidad.
* **Controladores:** Manejan estrictamente la lógica HTTP y el enrutamiento.
* **Servicios:** Encapsulan la lógica de negocio y las reglas de la economía virtual.
* **Repositorios:** Abstrae la capa de persistencia Serverless de PostgreSQL.
* **Motor de Auto-Recuperación (Auto-Healing):** Capa en segundo plano diseñada para resolver inconsistencias de datos mapeando IDs únicos en lugar de cadenas de texto volátiles.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 💻 Stack Tecnológico <a name="stack-tecnologico"></a>
* **Frontend:** React 19, Vite, Tailwind CSS 4, Framer Motion, React Router v7.
* **Backend:** Node.js, Express v5.0, `node-cron`.
* **Base de Datos:** PostgreSQL (Alojada en Neon para escalabilidad Serverless).
* **Infraestructura:** Railway (App en producción y alojamiento de Rocket.Chat).
* **APIs e Integraciones:** Stripe, API de Google Meet, API de Rocket.Chat, Nodemailer.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 🧗 Profundidad Técnica: Sincronización Chronos & Ghost <a name="profundidad-tecnica"></a>
La hazaña de ingeniería más compleja de esta plataforma fue resolver la **Hidratación de Sesiones** (El problema de Sincronización Ghost). 

Cuando los nombres de las clases cambiaban en la base de datos, los scripts de grabación automatizada "perdían" la conexión con los archivos de video. 

**La Solución de Ingeniería:** Construí un Motor de Mapeo de Auto-Recuperación (Self-Healing) que utiliza el código único de Google Meet como la "Fuente de Verdad" absoluta. Esto reconecta las sesiones huérfanas al `class_id` correcto, asegurando que la automatización nunca se rompa, sin importar los errores administrativos humanos.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 🔒 Seguridad y Cumplimiento <a name="seguridad"></a>
* **Escudo de Comunicaciones:** Filtrado RegEx en tiempo real en la capa de comunidad para prevenir la "Fuga de Negocio", bloqueando números de teléfono y palabras clave de pagos externos.
* **Integridad de Transacciones:** Implementación de transacciones SQL atómicas para la Billetera, asegurando que ningún estudiante pueda gastar créditos dos veces o reservar sin saldo válido.
* **Autenticación Stateless:** Implementación segura de JWT que garantiza sesiones protegidas incluso en entornos escalados horizontalmente.
* **Cumplimiento Normativo:** Privacidad y arquitectura de datos alineadas con la LFPDPPP (México) y los principios generales del GDPR.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 🔒 Política de Acceso al Código <a name="acceso-codigo"></a>
El código fuente de este proyecto es **Propiedad Privada**. Contiene lógica de negocio confidencial relacionada con pasarelas de pago, filtrado de comunidad y el sistema de créditos.

Estoy disponible para un **Recorrido Técnico en Vivo (Deep-Dive)** a través de una pantalla compartida para demostrar el Motor de Auto-Recuperación, las transacciones de PostgreSQL y la arquitectura de backend.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 👥 Autores <a name="autores"></a>

👤 **Sebastian Hernandez**
* **Rol:** Lead Full-Stack Engineer / Arquitecto
* **Agencia:** [Elevate Agency](https://your-elevate-link.com)
* **LinkedIn:** [Sebastian Hernandez](https://www.linkedin.com/in/sebastian-hernandez-munoz/)
* **GitHub:** [@your-github](https://github.com/shm04)

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

## 📝 Licencia <a name="licencia"></a>
Este proyecto es de **Propiedad Privada y Código Cerrado**. Todos los derechos reservados.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>
