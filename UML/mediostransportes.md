@startuml
scale 2

abstract class MediosTransporte{
    -color: String
    -longitud,cantidadPasajeros: Double
    +dejarPasajeros(pasajeros), recogerPasajero(pasajeros): int
    +recibirMantenimineto(): void

}

class TransporteAcuatico{
    -potenciaMotor, tipoPropulsion, materialTransporte: String
    +encenderMotor ():void
    +abastecerCombustible (litros): int
    +modificarRuta(ruta): String 
}

class Barco {
    -color,nombre: String
    -tripulación: int
    +remar(): void
    +abordar(): void
    +navegar(): void 
}

class Trajinera {
    -color, nombre: String
    -capacidad: int
    +remar():void
    +abordar():void
    +navegar():void 
    }

MediosTransporte <|-- TransporteAcuatico
TransporteAcuatico <|-- Barco: interfaz
TransporteAcuatico <|-- Trajinera: interfaz

class TransporteTerrestre{
    -numeroLlantas, numeroVentanas: int
    -kilometraje: Double
    +frenar(): void
    +acelerar(): void
    +encender():void 
}

class Subterraneo {
    -tipoLlantas:String
    -numeroUnidades: int
    -velocidadMax: Double
    +abrirPuertas():void
    +cerrarPuertas():void
    +informarProblemas():void
}

class Metro{
    -linea:String
    -numeroVagones, numeroEstaciones:int
    +realizarLimpieza(): void
    +inofrmarProblema():void
    +verificarSeguridad():void 
}
class Suburbano{
    -materialVagones, conductorAsignado: String
    -publicidadInterna: Boolean 
    +abordar(): void
    +bajar(): void
    +recorrer(): void
}

class Supraterraneo {
    -tarifa: Double
    -anuncioSonoro, estadoLimpieza: String
    +frenar():void
    +chocar():void
    +acelerar():String
}

class Taxi {
    -placas, color, modelo: String
    +avanzar(): void
    +frenar(): void
    +recoger(): void
}

class Combi {
    -numPasajero, ruta: int
    -destino: String
    +acelerar(): void
    +frenar(): void
    +chocar(): void
}
MediosTransporte <|-- TransporteTerrestre
TransporteTerrestre <|-- Subterraneo: interfaz 
TransporteTerrestre <|-- Supraterraneo: interfaz 
Subterraneo <|-- Metro: interfaz
Subterraneo <|-- Suburbano: interfaz
Supraterraneo <|-- Taxi : interfaz
Supraterraneo <|-- Combi : interfaz


class TransporteAereo{
    -alcance: Double
    -cantidadMotores: int
    -tipoAeronave: String
    +aterrizar(): void
    +despegar(): void
    +pilotoAutomatico(): void
}

class Avion{
    -modelo,diseñoInterior: String
    -añoFrabricación: int
    +despegar(): void
    +aterrizar(): void
    +girar(): void
}

class Helicoptero{
    -asiento,  pasajeros: int
    -modelo: String
    +despegar(): void
    +aterrizar(): void
    +acelerar(): void
}
MediosTransporte <|-- TransporteAereo
TransporteAereo <|-- Avion: interfaz
TransporteAereo <|-- Helicoptero: interfaz

