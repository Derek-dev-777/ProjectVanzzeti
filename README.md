```mermaid
classDiagram
    class PacienteEntity {
        Long id
        String name
        Integer age
        String diagnostico
        Enum tamanho (Baby, Infantil, Juvenil, GG)
        CadeiraEntity cadeira
    }

    class TecnicoEntity {
        Long id
        String name
        Integer age
        Enum cargo (Senior, Pleno, Junior)
        List~CadeiraEntity~ cadeirasFeitas
    }

    class CadeiraEntity {
        Long id
        String modelo
        Double preco
        Enum tamanho
        PacienteEntity paciente
        TecnicoEntity tecnico
    }

    PacienteEntity --> CadeiraEntity : possui
    TecnicoEntity --> "0..*" CadeiraEntity : fabrica
    CadeiraEntity --> PacienteEntity : destinada a
    CadeiraEntity --> TecnicoEntity : feita por
