usecaseDiagram
    actor "Usuario" as U
    actor "Sistema" as S

    rectangle "Módulo de Gestión de Perfil" {
        usecase "Ingresar al Perfil" as UC1
        usecase "Modificar Datos del Perfil" as UC2
        usecase "Ingresar Datos al Perfil" as UC3
        usecase "Eliminar Datos del Perfil" as UC4
    }

    rectangle "Módulo de Reportes" {
        usecase "Ingresar Nuevo Registro\n(tipo_reporte, fecha_generacion)" as UC5
        usecase "Asignar Datos Automáticos\n(usuario_id, reporte_id)" as UC6
    }

    U --> UC1
    UC1 --> UC2 : <<include>>
    UC1 --> UC3 : <<include>>
    UC1 --> UC4 : <<include>>

    U --> UC5
    UC5 ..> UC6 : <<extend>>
    UC6 --> S : Ejecuta
