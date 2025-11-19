# ***Mantenimiento Propuesto para el Sistema de Registro de usuario***

## ***1. Problema: Fallos en la validación de contraseñas***



  El sistema permite registrar contraseñas que no cumplen con los requisitos mínimos (longitud, complejidad, combinación de caracteres), lo que reduce la seguridad del sistema.



  ***Tipo de Mantenimiento:*** Mantenimiento correctivo

  

  ***Acción Principal:*** Optimizar las consultas SQL utilizadas durante el registro, implementar índices en campos clave, mejorar la arquitectura de acceso a datos y reducir operaciones innecesarias en el flujo de registro.



  ***Justificación Técnica:*** El problema no es un error, sino un rendimiento insuficiente respecto a lo esperado. La optimización mejora la velocidad del sistema, reduce la carga del servidor y eleva la calidad de la experiencia del usuario, contribuyendo a un mejor desempeño general de la aplicación.



## ***2. Problema: Correos de verificación no llegan al usuario***



  El sistema envía correos de verificación al momento del registro, pero en muchos casos estos no llegan o se marcan como spam, impidiendo que el usuario complete el proceso.



  ***Tipo de Mantenimiento:*** Mantenimiento adaptativo



  ***Acción Principal:*** Configurar correctamente el servidor de correo o cambiar a un servicio de envío más confiable (como SendGrid, Amazon SES o Mailgun). Implementar autenticaciones como SPF, DKIM y DMARC para asegurar la entrega, y optimizar el contenido del correo para evitar filtros de spam.



  ***Justificación Técnica:*** El fallo se debe a incompatibilidades o restricciones externas del servicio de correo, no a errores internos del sistema. Ajustar la configuración garantiza una correcta integración con proveedores de email, mejora la tasa de entrega y permite que los usuarios completen el registro sin inconvenientes.


