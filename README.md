## Diagrama Entidad-Relación (DER) - VetCare

```mermaid
erDiagram
    PROPIETARIO ||--o{ MASCOTA : "tiene"
    MASCOTA ||--o{ CITA_MEDICA : "asiste a"
    VETERINARIO ||--o{ CITA_MEDICA : "atiende"

    PROPIETARIO {
        int id_propietario PK "AI"
        string nombre
        string telefono
        string email
        string direccion
    }

    MASCOTA {
        int id_mascota PK "AI"
        string nombre
        string especie
        string raza
        int edad
        int id_propietario FK
    }

    VETERINARIO {
        int id_veterinario PK "AI"
        string nombre
        string especialidad
        string telefono
    }

    CITA_MEDICA {
        int id_cita PK "AI"
        date fecha
        time hora
        string motivo
        int id_mascota FK
        int id_veterinario FK
    }

