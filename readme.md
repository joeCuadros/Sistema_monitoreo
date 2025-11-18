# Comandos a ejecutar

```vdmpp
tcov reset
```

```vdmpp
create mon := new Monitor(16,11,2025)
```

```vdmpp
print mon.cargarDatos()
```

```vdmpp
print mon.cargarFechas()
```

```vdmpp
print mon.obtenerDatosEstudiante(mk_token(20223014))
```

```vdmpp
print mon.obtenerEdadEstudiante(mk_token(20220575))
```

```vdmpp
print mon.obtenerEdadEstudiante(mk_token(20222067))
```

```vdmpp
print mon.obtenerEdadEstudiante(mk_token(20260001))
```

```vdmpp
print mon.obtenerEdadEstudiante(mk_token(20260002))
```

```vdmpp
print mon.obtenerEdadEstudiante(mk_token(20260003))
```

```vdmpp
print mon.obtenerDatosDocente(mk_token(153))
```

```vdmpp
print mon.cargarInscripciones()
```

```vdmpp
print mon.obtenerEstudiantesCurso(mk_token("AFEV"))
```

```vdmpp
print mon.totalEstudiantesCurso(mk_token("AFEV"))
```

```vdmpp
print mon.cargarEvaluaciones()
```

```vdmpp
print mon.obtenerNotas(mk_token(1))
```

```vdmpp
print mon.cargarAsistencias()
```

```vdmpp
print mon.obtenerAsistencias(mk_token(1))
```

```vdmpp
print mon.analizarRiesgoSistema()
```

```vdmpp
print mon.analizarRiesgoSistema()
```

```vdmpp
print mon.obtenerAlertas()
```

```vdmpp
print mon.obtenerTiposAlertas(<BajoRendimiento>)
```

```vdmpp
print mon.obtenerAlertasCurso(mk_token("AFEV"))
```

```vdmpp
print mon.obtenerAlertasEstudiante(mk_token(20222067))
```

```vdmpp
print mon.obtenerAlertasDocente(mk_token(153))
```

```vdmpp
print mon.cargarAlertas()
```

```vdmpp
print mon.analizarRiesgoSistema()
```

```vdmpp
tcov write vdm.tc
```

```vdmpp
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