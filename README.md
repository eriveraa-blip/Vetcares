# 🐾 VetCare - Sistema de Gestión Veterinaria

Este repositorio contiene el diseño de la base de datos para la clínica veterinaria VetCare, automatizando los procesos de propietarios, mascotas, veterinarios y citas médicas.

---

## 📊 1. Diagrama Entidad-Relación (DER)

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
