# Resumen del Sistema de Registro de Usuarios

## Descripcion del caso 

El Sistema de Registro de Usuarios tiene como propósito principal establecer una puerta de acceso segura y confiable para nuestra plataforma, gestionando la identidad digital de cada usuario desde su registro inicial hasta su autenticación y gestión de perfil



## Objetivo del sistema 
El objetivo principal del Sistema de Registro de Usuarios es establecer una puerta de acceso segura y confiable para la plataforma.

Su propósito se centra en:

* Gestionar la identidad digital de cada usuario, desde el registro inicial hasta su autenticación y gestión de perfil.
* Imponer políticas de contraseñas robustas.


## REQUERIMIENTOS

### Requerimientos Funcionales (RF)
* RF1 - Bloquear temporalmente la cuenta tras 5 intentos fallidos de inicio de sesión.

* RF2 - Mostrar la fecha, hora e IP del último acceso para seguridad.

* RF3 - Rechazar el registro si se usa un correo electrónico temporal.

* RF4 - Permitir al usuario la desactivación reversible de su cuenta (datos retenidos 90 días).

* RF5 - Ofrecer formularios de registro e inicio de sesión en al menos español e inglés.


### Requerimientos Funcionales (RNF)
* RNF1 - Seguridad: Almacenamiento de tokens solo en cookies seguras.

* RNF2 - Compatibilidad: Interfaz responsiva en los principales navegadores.

* RNF3 - Usabilidad: Mensajes de error específicos junto al campo de formulario afectado.


# Casos de prueba (sin tabla)



---

**CP1**

* **Tipo:** Unitario
* **Requerimiento asociado:** Registro de nuevo usuario (datos válidos).
* **Datos:** Nombre: Ana Pérez, Correo: anaperez@email.com, Contraseña: P@sswOrd123.
* **Resultado esperado:** Registro exitoso y usuario guardado.
* **Resultado obtenido:** Éxito.

---

**CP2**

* **Tipo:** Unitario
* **Requerimiento asociado:** Correo electrónico único.
* **Datos:** Intento de registro con correo ya existente (anaperez@email.com).
* **Resultado esperado:** Rechazo y error por duplicidad.
* **Resultado obtenido:** Error: El correo electrónico ya está registrado.

---

**CP3**

* **Tipo:** Unitario
* **Requerimiento asociado:** Longitud mínima de contraseña (8 caracteres).
* **Datos:** Contraseña demasiado corta (corto123 - 7 caracteres).
* **Resultado esperado:** Rechazo y error por longitud mínima.
* **Resultado obtenido:** Error: La contraseña debe tener al menos 8 caracteres.

---

**CP4**

* **Tipo:** Validación
* **Requerimiento asociado:** Campos obligatorios (Nombre).
* **Datos:** Intento de registro con el campo Nombre vacío.
* **Resultado esperado:** Error de validación: El campo Nombre es obligatorio.
* **Resultado obtenido:** Éxito (Error de Validación mostrado).

---

**CP5**

* **Tipo:** Validación
* **Requerimiento asociado:** Formato de correo válido.
* **Datos:** Correo inválido (correoinvalido.com - sin '@').
* **Resultado esperado:** Error de validación: Formato de correo incorrecto.
* **Resultado obtenido:** Éxito (Error de Validación mostrado).


## Tipo de Mantenimiento Propuesto

* Correctivo: Corregir errores detectados en operación. Ejemplo: Parches y bug fixes. 
* Adaptativo: Ajustar el sistema a nuevos entornos o requisitos externos. Ejemplo: Compatibilidad con nuevo SO o hardware. 
* Perfectivo: Mejorar rendimiento o añadir funciones. Ejemplo: Optimizar código o agregar módulos. 
* Preventivo: Prevenir errores futuros y mejorar mantenibilidad. Ejemplo: Refactorización, limpieza del código.

## Reflexión sobre el Control de Versiones
El control de versiones es fundamental para un sistema que gestiona la identidad digital y la seguridad, ya que proporciona la trazabilidad necesaria para auditar cada cambio en funciones críticas como la autenticación y el cifrado de contraseñas, lo cual es esencial para mantener la coherencia y la responsabilidad en el código. Además, facilita la verificación empírica de los requisitos al correlacionar los commits directamente con los casos de prueba y los criterios de aceptación, asegurando que el sistema cumpla con las especificaciones de seguridad y rendimiento y transformando los requisitos teóricos en funcionalidad demostrable.
 
