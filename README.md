```mermaid
graph TD
    %% Estilos y Actores
    subgraph Actores
        U([Usuario])
        S([Sistema])
    end

    subgraph Módulo de Gestión de Perfil
        UC1[Ingresar al Perfil]
        UC2[Modificar Datos del Perfil]
        UC3[Ingresar Datos al Perfil]
        UC4[Eliminar Datos del Perfil]
    end

    subgraph Módulo de Reportes
        UC5[Ingresar Nuevo Registro<br/>(tipo_reporte, fecha_generacion)]
        UC6[Asignar Datos Automáticos<br/>(usuario_id, reporte_id)]
    end

    %% Relaciones Perfil
    U --> UC1
    UC1 -.->|<<include>>| UC2
    UC1 -.->|<<include>>| UC3
    UC1 -.->|<<include>>| UC4

    %% Relaciones Reportes
    U --> UC5
    UC6 -.->|<<extend>>| UC5
    UC6 --> S
