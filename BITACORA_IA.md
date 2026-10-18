# Bitácora de Uso de Inteligencia Artificial - Práctica 2
**Materia:** Programación Avanzada / POO 2
**Repositorio:** `practica2/BITACORA_IA.md

## 1. Desarrollo Orientado a Objetos y Guía Paso a Paso del Código

### **Prompt / Solicitud enviada a la IA por el equipo:**
> "Ayúdanos a construir la práctica paso a paso. Queremos guiar la programación nosotros mismos para entender cada línea de código y estar preparados para la defensa presencial."

### **Orientación y Proceso de Aprendizaje del Equipo:**
1. **Selección de la Arquitectura:** Elegimos desarrollar un *Sistema de Control Térmico* (Opción B) compuesto por `Sensortemperatura`, `Ventilador`, `Bateria` y la clase compuesta `Sistematermico`.
2. **Encapsulamiento y Validaciones (`@property`):**
   * Definimos el uso de atributos privados (ej. `_temperatura`, `_potencia`, `_voltaje`) para aislar los datos.
   * La IA nos explicó cómo funciona el decorador `@property` (getter) como interfaz de lectura y el `@property.setter` como filtro de entrada.
   * Implementamos validaciones de rangos físicos reales levantando `ValueError` con mensajes claros ante lecturas o entradas imposibles.
3. **Métodos Útiles y Presentación (`__str__`):**
   * Agregamos métodos de monitoreo y banderas lógicas (`actualizar_tem`, `sobrecalentamiento`, `ajustar_potencia`, `esta_girando`, `bateria_baja`).
   * Implementamos `__str__` en todas las clases para reportar magnitudes y unidades físicas reales (`°C`, `%`, `V`).
4. **Composición y Delegación:**
   * Diseñamos la clase `Sistematermico` para recibir e integrar los componentes físicos en su constructor (`__init__`).
   * Programamos `control_automatico()` demostrando la delegación al coordinar la lectura del sensor y la activación del ventilador.
5. **Sobrecarga de Operadores (Regla de Oro):**
   * Implementamos `__gt__` en `Sensortemperatura` para comparar lecturas térmicas entre dos sensores.
   * Implementamos `__add__` en `Bateria` para simular la conexión en serie de dos celdas, retornando una nueva instancia de `Bateria` ("Arreglo en Serie") con el voltaje total sumado.
6. **Pruebas de Validación y Manejo de Excepciones (`try/except`):**
   * La IA nos guio en la creación del bloque `demo` para probar la ejecución automática, el uso de operadores y la captura segura de un `ValueError` mediante `try/except` al inyectar un voltaje destructivo.

---

## 2. Reflexión y Aprendizaje del Equipo
* **Composición sobre Herencia:** Reafirmamos el concepto de *"tiene-un"* entre `Sistematermico` y sus componentes.
* **Seguridad y Robustez:** Aprendimos la importancia de las cláusulas de guarda, el aislamiento de atributos y el manejo de excepciones para evitar el colapso del programa.
* **Preparación para la Defensa:** El desarrollo guiado nos permitió a todos los integrantes comprender el flujo de ejecución, la notación UML y las decisiones de diseño POO.

---

## 3. Consulta y Diseño del Diagrama UML

### **Prompt / Solicitud enviada a la IA:**
> "Ayúdanos a hacer el diagrama UML con la información de nuestro código, danos las instrucciones a seguir para realizar el diseño del diagrama. Ya tenemos las clases `Sensortemperatura`, `Ventilador`, `Bateria` y la clase compuesta `Sistematermico`."

### **Respuesta y Orientación de la IA:**
* La IA analizó las 3 clases de componentes y la clase compuesta (`Sistematermico`).
* Identificó la relación de **composición** entre la clase compuesta y sus componentes.
* Nos proporcionó la estructura en código **Mermaid** configurando la sintaxis adecuada para la relación de composición (`*--`), la multiplicidad (`1`) y detallando los atributos, visibilidad (`+` / `-`) y métodos de cada clase.
* Nos indicó el procedimiento para renderizar el código en *Mermaid Live Editor*, verificar el rombo relleno (`◆`) de composición y exportar la imagen como `uml.png` para cumplir con los requisitos del repositorio.

### **Ajustes y Resultado Final:**
* Se ingresó el código Mermaid en la plataforma recomendada (*Mermaid Live Editor*).
* Se verificó visualmente que la composición y la multiplicidad (1:1) coincidieran exactamente con la arquitectura de código implementada.
* Se confirmó la correcta representación de las *properties*, getters/setters y sobrecarga de operadores.
* Se exportó la imagen final como `uml.png` y se integró en la carpeta `practica2/`.

---

## 4. Reflexión y Aprendizaje del Equipo
* La interacción con la IA nos ayudó a traducir la estructura del código en Python a una representación estándar en UML.
* Aprendimos a identificar la notación de composición (rombo relleno `◆`) frente a la agregación o herencia, reafirmando el concepto de *"tiene-un"* entre `Sistematermico` y sus componentes.
