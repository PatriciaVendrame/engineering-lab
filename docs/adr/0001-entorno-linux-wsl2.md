# ADR-0001: Entorno Linux para el laboratorio

## Contexto

El laboratorio DevSecOps & AI Engineering Lab requiere un entorno Linux para aprender y practicar herramientas utilizadas en DevOps, DevSecOps, automatización e infraestructura.

El equipo de trabajo utiliza Windows 11 como sistema operativo principal, por lo que necesitamos disponer de Linux sin reemplazarlo ni incorporar complejidad innecesaria.

El entorno debe permitir ejecutar comandos, administrar archivos y permisos, utilizar herramientas de desarrollo y realizar pruebas prácticas en condiciones similares a las que podemos encontrar en entornos profesionales.

En esta etapa, no necesitamos administrar múltiples máquinas virtuales ni reproducir una infraestructura completa de producción. Priorizamos una solución sencilla, integrada con Windows y adecuada para los primeros laboratorios.

## Decisión

Utilizaremos Windows Subsystem for Linux 2 (WSL2) para disponer de un entorno Linux integrado con Windows 11, sin reemplazar el sistema operativo principal.

La distribución seleccionada es Ubuntu 24.04 LTS, sobre la cual instalaremos y configuraremos progresivamente las herramientas necesarias para los laboratorios.

Los proyectos y repositorios Git se almacenarán dentro del sistema de archivos de Ubuntu, manteniendo separado el espacio de trabajo Linux de los directorios habituales de Windows.

Esta configuración será nuestro entorno inicial de desarrollo y aprendizaje. Podrá revisarse cuando los requisitos de los proyectos demanden una infraestructura diferente.

## Justificación

Se seleccionó WSL2 porque permite trabajar con un entorno Linux desde Windows 11 sin necesidad de reemplazar el sistema operativo principal ni administrar una máquina virtual tradicional.

Esta alternativa ofrece una preparación relativamente sencilla, integración con el entorno Windows y acceso a sus archivos cuando sea necesario.

Para la etapa inicial del laboratorio, WSL2 proporciona las capacidades necesarias para practicar comandos Linux, permisos, Git, scripting y otras herramientas de ingeniería que incorporaremos progresivamente.

Se consideraron como alternativas las máquinas virtuales tradicionales, mediante herramientas como VirtualBox o VMware, y el uso de equipos o servidores Linux independientes. Estas opciones pueden ofrecer mayor control sobre la infraestructura, pero actualmente introducirían complejidad adicional sin una necesidad técnica concreta.

## Consecuencias

### Ventajas

- Disponemos de un entorno Linux sin reemplazar Windows 11.
- Podemos practicar herramientas de ingeniería y automatización sin administrar una máquina virtual tradicional.
- Mantenemos una integración sencilla entre Windows y Ubuntu.
- Podemos desarrollar y versionar nuestros proyectos directamente en el sistema de archivos Linux.

### Limitaciones y riesgos

- WSL2 no reproduce todas las características de un servidor Linux independiente ni de una infraestructura de producción.
- Las pruebas con topologías de red complejas o múltiples sistemas operativos pueden requerir máquinas virtuales o entornos adicionales.
- Aunque WSL2 utiliza virtualización, no debemos considerarlo un entorno completamente aislado para ejecutar software potencialmente malicioso.
- El rendimiento y la disponibilidad de recursos dependen también del equipo anfitrión.

### Criterio de revisión

Reevaluaremos esta decisión cuando un proyecto necesite características que WSL2 no proporcione adecuadamente, como configuraciones avanzadas de red, aislamiento adicional, infraestructura distribuida o pruebas que requieran mayor similitud con producción.
