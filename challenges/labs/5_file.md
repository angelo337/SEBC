Autenticacion: en autenticacion el sistema de Claoudera usa para autenticacion integracion con Kerberos tanto para servicios como para usuarios, se puede utiluzar MIT KERBEROS o MS Kerberos con Directorio Activo (AD)

Autorizacion: la autorizacion depende de la forma en que se realice la autenticacion si se realiza con AD es la mas sencilla de administrar, una vez integrado se dan permisos sobre los recursos generales del sistema y se logra tener granularida y seguimiento de los mismos.

No repudio (Accountability): el no repudio se logra con la instalacion de NAVIGATOR producto solo disponible en la verson LICENCIADA DE CLOUDERA, en la que se lleva el seguimineto de todas las actividades realizadas por los diferentes usuarios y servicios sobre la informacion y su registro.

Privacidad: se logra con la implmentacion de TLS/SSL en la informacion en transito y la implmentacion de encripcion en la informacion en reposo.

en un cluster con seguridad solo se usa la interfaz de red asociada al FQDN de cada nodo, para todo trafico relacionado con HADOOP, en caso de duda consultar con CLOUDERA.
