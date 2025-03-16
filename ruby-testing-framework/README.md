# TADsSpec - Framework de Testing en Ruby

## Descripción
TADsSpec es un framework de testeo desarrollado en Ruby que permite realizar pruebas utilizando un DSL intuitivo y flexible. Su objetivo es facilitar la verificación de postcondiciones dentro de tests, ofreciendo aserciones expresivas y herramientas para mocks y spies.

Este framework se construyó aplicando conceptos de metaprogramación y buenas prácticas de diseño, garantizando una sintaxis limpia y extensible.

---

## Características principales

### Aserciones
- `ser`: Verifica igualdad de valores.
- `ser_igual`: Compara estrictamente valores.
- `ser mayor_a` / `ser menor_a`: Compara rangos de valores.
- `ser uno_de_estos`: Verifica si un valor está dentro de una lista.
- `tener_<atributo>`: Comprueba el estado interno de un objeto.
- `entender`: Valida si un objeto responde a un mensaje.
- `explotar_con`: Testea que un bloque lance una excepción esperada.

### Tests y Suites
- Los tests son métodos cuyo nombre comienza con `testear_que_`.
- Los tests se agrupan en suites representadas por clases.
- Se pueden ejecutar tests individuales, suites completas o todas las suites en contexto.
- Resultados posibles:
  - **Test pasado** ✅
  - **Test fallido** ❌
  - **Test explotado** 💥

### Mocking y Spying
- `mockear`: Reemplaza temporalmente la implementación de un método dentro de un test.
- `espiar(objeto)`: Permite inspeccionar los mensajes recibidos por un objeto durante un test.
- `haber_recibido`: Verifica que un objeto espiado haya recibido ciertos mensajes.

---

## Ejemplo de Uso

```ruby
class Persona
  attr_accessor :edad
  def viejo?
    @edad > 29
  end
end

class PersonaTest
  def testear_que_una_persona_es_vieja
    persona = Persona.new
    persona.edad = 30
    persona.deberia ser_viejo
  end
end
```

---

## Resultados de Test
_Agrega aquí capturas de pantalla de los distintos resultados de los tests._

### Test Pasado ✅
_Agregar imagen_

### Test Fallido ❌
_Agregar imagen_

### Test Explotado 💥
_Agregar imagen_

---

## Ejecución
Ejecutar todos los tests:
```sh
TADsSpec.testear
```

Ejecutar una suite en particular:
```sh
TADsSpec.testear MiSuite
```

Ejecutar un test específico:
```sh
TADsSpec.testear MiSuite, :testear_que_una_persona_es_vieja
```

---

## Contribución
El framework está diseñado para ser extensible. Puedes agregar nuevas aserciones y funcionalidades utilizando la metaprogramación de Ruby.

Si tienes sugerencias o mejoras, ¡serán bienvenidas!

---

## Licencia
Este proyecto es de código abierto y puede utilizarse libremente para fines académicos o profesionales.

