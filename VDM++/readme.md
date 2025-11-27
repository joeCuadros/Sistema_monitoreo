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


```vpp
tcov reset
create test := new Test()
print test.ProbarTodos()
tcov write vdm.tc
rtinfo vdm.tc
```

## Grafico de clases

```mermaid
classDiagram
class Fecha {
    - dia : nat
    - mes : nat
    - anio : nat
    + getDia() : nat
    + getMes() : nat
    + getAnio() : nat
    + calcularDiferencia(fecha : Fecha) ==> nat
}

class Estudiante {
    - codigo : token
    - nombres : seq of char
    - apellidos : seq of char
    - fecha_nacimiento : Fecha
    + getDatos() ==> seq of char
    + getEdad(fecha : Fecha) ==> nat
}

class Docente {
    - codigo : token
    - nombres : seq of char
    - apellidos : seq of char
    + getDatos() ==> seq of char
}

class Curso {
    - codigo : token
    - docente : token
    - estudiantes : set of token
    + inscribirEstudiante(cod_est : token) ==> ()
    + retirarEstudiante(cod_est : token) ==> ()
    + getEstudiantes() ==> set of token
    + isMatriculado(cod_est : token) ==> bool
    + getDocente() ==> token
    + getCodigo() ==> token
}

class Asistencia {
    - curso : token
    - fecha : Fecha
    - estado : <Creado> | <Proceso> | <Finalizado>
    - contenido : map token to bool
    + registrarAsistencia(cod_est : token, asistio : bool) ==> ()
    + getAsistencias() ==> map token to bool
    + getCurso() ==> token
    + terminar() ==> ()
    + termino() ==> bool
}

class Evaluacion {
    - tipo : <Examen> | <Practica> | <Tarea> | <Proyecto>;
    - curso : token
    - fecha : Fecha
    - estado : <Creado> | <Proceso> | <Finalizado>
    - contenido : map token to real
    + agregarNota(cod_est : token, nota : real) ==> ()
    + getAsistencias() ==> map token to real
    + getCurso() ==> token
    + terminar() ==> ()
    + termino() ==> bool
}

class Alerta {
    - estudiante : token
    - docente : token
    - curso : token
    - tipo : <BajoRendimiento> | <Inasistencia> 
    | <FaltaEvaluacion> | <AdvertenciaGeneral>
    - descripcion : seq of char
    - estado : <Creado> | <Pendiente> 
    | <Concluido> | <Archivado>
    + esRepetido(est : token, doc : token, cod_cur : token, tip: tipoAlerta) ==> bool
    + terminar(estado_nuevo: estadoAlerta) ==> ()
    + verificarEstado(estado_verificar: estadoAlerta) ==> bool
}

Estudiante --> Fecha : usa
Docente --> Fecha : usa
Curso ..> Estudiante : usa codigos
Curso ..> Docente : usa codigo
Asistencia --> Fecha : usa
Asistencia ..> Estudiante : usa codigos
Asistencia ..> Curso : usa codigo
Evaluacion --> Fecha : usa
Evaluacion ..> Estudiante : usa codigos
Evaluacion ..> Curso : usa codigo
Alerta ..> Estudiante : usa codigos
Alerta ..> Docente : usa codigos
Alerta ..> Curso : usa codigo
```

