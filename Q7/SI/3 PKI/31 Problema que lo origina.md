Debido a la posibilidad de "secuestro" de las claves, pudiendo la gente hacerse pasar por otra dando una clave pública propia en lugar de la que debe ser es necesario poder certificar que la clave es la de la persona que dice ser.

## Propuestas

### Primera

Único repositorio seguro que almacena todas las claves públicas. Tiene problemas de rendimiento, necesidad de seguridad externa y la necesidad de backups que requiere la transmisión de nuevos datos constantemente.

### Segunda

Uso de autoridades de confianza centralizadas que permitan crear un conjunto de registros de datos firmados (certificados) que permitan un sistema de distribución de claves públicas.

#### Certificados

- Identidad del propietario
- Clave pública
- Firma digital de una entidad de confianza que lo certifica

De esta manera la confianza que se tiene en esta autoridad se pasa a la clave pública