## ¿Cómo separan la identidad del votante del contenido del voto sin perder el control de duplicados?**

- Control de duplicados: Se utiliza el padrón electoral vinculado al sistema académico para validar que el estudiante está matriculado y marcar un indicador de estado.

- Anonimato: Para separar la identidad, este registro de control nunca se almacena junto con el voto. Se implementa un esquema desacoplado o de tokens donde el sistema verifica la elegibilidad del usuario, le permite emitir el voto de forma anónima hacia una urna digital independiente, y destruye cualquier rastro de la relación entre el votante y su papeleta.



## Un veedor exige verificar que el conteo es correcto. ¿Qué le muestran sin revelar votos individuales?

- Pruebas de integridad: Se le muestran registros de auditoría que garantizan que los votos almacenados no han sido alterados ni eliminados.


- Reportes agregados: Se presentan actas de escrutinio desglosadas por totales globales o por facultad (siempre que el volumen de votantes en dicha facultad preserve el anonimato), permitiendo comprobar matemáticamente que el número de votos registrados coincide exactamente con el conteo final sin exponer la preferencia de ningún estudiante.


## Si el sistema se cae durante la jornada, ¿se pierden votos? ¿Cuál es su pérdida máxima aceptable?

- Pérdida de votos: No se pueden perder votos bajo ninguna circunstancia. Dado que la votación ocurre en una única jornada crítica con alta concurrencia, la base de datos y la arquitectura deben garantizar transacciones seguras con persistencia inmediata antes de confirmar el éxito al votante.


- Pérdida máxima aceptable en disponibilidad: Aunque una falla en la infraestructura puede generar interrupciones temporales (afectando el tiempo de recuperación), la pérdida de datos de votos ya emitidos y confirmados es inaceptable, por lo que se requiere alta disponibilidad, bases de datos replicadas y mecanismos de tolerancia a fallos.