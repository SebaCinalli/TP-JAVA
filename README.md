# PROPUESTA TP JAVA

## Grupo:

### Integrantes

  * **Legajo: 52170** - Apellido y Nombre: Salvucci, Nahuel
  * **Legajo: 52053** - Apellido y Nombre: Cinalli, Sebastian

### Repositorios

- [Frontend App](https://github.com/nanosalvu11/Java-FrontEnd)
- [Backend app](https://github.com/nanosalvu11/Java-Backend)

### Descripcion

El proyecto consiste en el desarrollo de una aplicación web que simulará un **Casino Virtual** interactivo.

La plataforma permitirá a los usuarios registrados gestionar una billetera virtual (ingreso y retiro de saldo) y participar en salas de juego de Ruleta y Blackjack. El sistema controlará en tiempo real el saldo de los jugadores para permitir o rechazar las apuestas, aplicando las reglas matemáticas y lógicas propias de cada juego.

A nivel administrativo, el sistema contará con un panel de control donde los administradores podrán gestionar los juegos disponibles, configurar los límites de las mesas (apuesta mínima y máxima) y visualizar reportes detallados sobre las estadísticas de ganancias y pérdidas del casino.


### Modelo

  * **Usuario:** ID, Nombre, Email, Password, Saldo, Rol (Jugador/Admin).
  * **Juego:** ID, Nombre (Ej: Ruleta, Blackjack), Reglas/Descripción. *(Entidad Simple)*
  * **Mesa:** ID, ID\_Juego, Apuesta\_Minima, Apuesta\_Maxima, Estado. *(Entidad Dependiente de Juego)*
  * **Apuesta:** ID, ID\_Usuario, ID\_Mesa, Monto\_Apostado, Resultado\_Monto, Fecha. *(Entidad Dependiente de Usuario y Mesa)*

## Alcance Funcional

Regularidad:
| Requerimiento | Cant. Mín. | Detalle / Listado de casos incluidos |
| :--- | :--- | :--- |
| **ABMC simple** | 2 | **1. Gestión de Usuarios:** (Admin) Alta, baja, modificación y consulta de usuarios.<br>**2. Gestión de Juegos:** (Admin) Definir los juegos base del casino. |
| **ABMC dependiente** | 1 | **1. Gestión de Mesas:** (Admin) ABMC de las mesas de juego, asignándolas a un Juego existente. |
| **CU NO-ABMC** | 1 | **1. Realizar Apuesta:** (Jugador) El sistema verifica que el usuario tenga saldo suficiente y que el monto esté dentro del límite permitido por la Mesa. |
| **Listado simple** | 1 | **1. Historial de Partidas:** (Jugador) Listado que cruza Apuesta, Mesa y Juego para mostrar al usuario su historial. |
| **Listado complejo** | 0 | *(No requerido para regularidad en grupos de 2)* |

Aprobación Directa
| Requerimiento | Cant. Mín. | Detalle / Listado de casos incluidos |
| :--- | :--- | :--- |
| **ABMC** | Todos | Se incluyen todos los detallados en la regularidad. |
| **CU "Complejo"** | 1 | **1. Ciclo de Partida de Blackjack:** 1) Repartir Cartas. 2) Toma de Decisión (Plantarse/Pedir). 3) Resolución y Transacción en BD. |
| **Listado complejo** | 1 | **1. Reporte de Recaudación:** (Admin) Ganancias/pérdidas del casino, filtrando por Fecha y Tipo de Juego. |
| **Nivel de acceso** | 2 | **1. Jugador:** Juega, deposita saldo y ve historial.<br>**2. Administrador:** Gestiona mesas, juegos y métricas. |
