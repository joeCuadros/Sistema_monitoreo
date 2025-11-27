# Comandos a ejecutar

Casos de pruebas 
1. Clase Fecha (considera que para la prueba se uso la fecha de 26/11/2025):

| Metodo             | Valores de entrada | Descripcion |
|:-------------------|:-------------------|:--------------|
| calcularDiferencia | fecha = 05/12/2005 | mes antes, dias antes|
| calcularDiferencia | fecha = 29/12/2005 | mes antes, dias despues|
| calcularDiferencia | fecha = 24/11/2004 | mismo mes, dias antes|
| calcularDiferencia | fecha = 27/11/2004 | mismo mes, dias despues|
| calcularDiferencia | fecha = 02/09/2005 | mes despues, dias antes|
| calcularDiferencia | fecha = 29/09/2005 | mes despues, dias despues|
| calcularDiferencia | fecha = 07/04/2004 | bisiesto (multiplo de 4)|
| calcularDiferencia | fecha = 28/02/1900 | no bisiesto (multiplo de 100) |
| calcularDiferencia | fecha = 05/02/2000 | bisiesto (multiplo de 400)|
| calcularDiferencia | fecha = 05/02/2025 | mismo año, mes antes, dia antes|
| calcularDiferencia | fecha = 25/02/2025 | mismo año, mes antes, dia despues|
| calcularDiferencia | fecha = 05/12/2025 | mismo año, mes igual, dia antes|


```
tcov reset
create test := new Test()
print test.ProbarFecha()
tcov write vdm.tc
rtinfo vdm.tc
```

## Comandos a ejecutar completo
```vdmpp
tcov reset
create mon := new Monitor(16,11,2025)
print mon.cargarDatos()
print mon.cargarFechas()
print mon.obtenerDatosEstudiante(mk_token(20223014))
print mon.obtenerEdadEstudiante(mk_token(20220575))
print mon.obtenerEdadEstudiante(mk_token(20222067))
print mon.obtenerEdadEstudiante(mk_token(20260001))
print mon.obtenerEdadEstudiante(mk_token(20260002))
print mon.obtenerEdadEstudiante(mk_token(20260003))
print mon.obtenerDatosDocente(mk_token(153))

print mon.cargarInscripciones()
print mon.obtenerEstudiantesCurso(mk_token("AFEV"))
print mon.totalEstudiantesCurso(mk_token("AFEV"))

print mon.cargarEvaluaciones()
print mon.obtenerNotas(mk_token(1))

print mon.cargarAsistencias()
print mon.obtenerAsistencias(mk_token(1))

print mon.analizarRiesgoSistema()
print mon.analizarRiesgoSistema()
print mon.obtenerAlertas()
print mon.obtenerTiposAlertas(<BajoRendimiento>)
print mon.obtenerAlertasCurso(mk_token("AFEV"))
print mon.obtenerAlertasEstudiante(mk_token(20222067))
print mon.obtenerAlertasDocente(mk_token(153))

print mon.cargarAlertas()
print mon.analizarRiesgoSistema()
tcov write vdm.tc
rtinfo vdm.tc
```