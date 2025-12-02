from abc import ABC, abstractmethod
from typing import Protocol

class Usuario(ABC):
    """
    Clase base abstracta (superclase) para cualquier entidad de usuario en el sistema.
    Aplica el principio de Abstracción al definir una interfaz común.
    """
    def __init__(self, nombre: str, correo: str):
        """Inicializa un objeto Usuario."""
        self._nombre = nombre
        self._correo = correo

    # Propiedades (getters) para acceso controlado a los atributos
    @property
    def nombre(self) -> str:
        """Retorna el nombre del usuario."""
        return self._nombre

    @property
    def correo(self) -> str:
        """Retorna el correo electrónico del usuario."""
        return self._correo
    
    @abstractmethod
    def mostrar_info(self) -> str:
        """
        Método abstracto que debe ser implementado por todas las subclases.
        Retorna la información específica de la instancia de usuario.
        """
        pass

# ----------------------------------------------------------------------

class IInformable(Protocol):
    """
    Interfaz (Protocolo) que define el contrato para cualquier objeto 
    capaz de generar un informe de sus datos internos.
    """
    def generar_informe(self) -> str:
        """
        Método de contrato. Retorna un string con el informe o estadísticas del objeto.
        """
        ...
