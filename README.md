En esta práctica, vamos a crear un sistema de gestión de empleados utilizando la programación orientada a objetos en Python.
Este sistema contendrá clases que representan diferentes tipos de empleados, como empleados regulares y gerentes, y exploraremos conceptos como herencia, polimorfismo y sobrecarga de métodos.



Pasos: Crear clases para calcular el salario de un empleado.
Puedes experimentar con los siguientes pasos para entender correctamente los conceptos relacionados con esta practica
Paso 1: Definición de Clases
•	Crea una clase Empleado con los siguientes atributos:
•	nombre
•	edad
•	salario_base
•	Crea los métodos siguientes:
•	__init__: un constructor que inicializa los atributos.
•	calcular_salario: un método que devuelve el salario base del empleado.
class Empleado:
    def __init__(self, nombre, edad, salario_base):
        self.nombre = nombre
        self.edad = edad
        self.salario_base = salario_base
 
    def calcular_salario(self):
        return self.salario_base
 
 
•	Crea una clase Gerente que herede de la clase Empleado. Esta clase debería tener un atributo adicional:
•	Bono
•	Sobrescribe el método calcular_salario en la clase Gerente para tener en cuenta el bono además del salario base.

class Gerente(Empleado):
    def __init__(self, nombre, edad, salario_base, bono):
        super().__init__(nombre, edad, salario_base)
        self.bono = bono
 
    def calcular_salario(self):
        return super().calcular_salario() + self.bono 


Paso 2: Implementación de Propiedades
•	Agrega propiedades para los atributos nombre, edad, y salario_base en la clase Empleado. Las propiedades deben tener métodos get y set.
•	Agrega una propiedad para el atributo bono en la clase Gerente con métodos get y set.
class Empleado:
    def __init__(self, nombre, edad, salario_base):
        self._nombre = nombre
        self._edad = edad
        self._salario_base = salario_base
 
    @property
    def nombre(self):
        return self._nombre
 
    @nombre.setter
    def nombre(self, nuevo_nombre):
        self._nombre = nuevo_nombre
 
    @property
    def edad(self):
        return self._edad
 
    @edad.setter
    def edad(self, nueva_edad):
        self._edad = nueva_edad
 
    @property
    def salario_base(self):
        return self._salario_base
 
    @salario_base.setter
    def salario_base(self, nuevo_salario):
        self._salario_base = nuevo_salario
 
    def calcular_salario(self):
        return self._salario_base
 
 
class Gerente(Empleado):
    def __init__(self, nombre, edad, salario_base, bono):
        super().__init__(nombre, edad, salario_base)
        self._bono = bono
 
    @property
    def bono(self):
        return self._bono
 
    @bono.setter
    def bono(self, nuevo_bono):
        self._bono = nuevo_bono
 
    def calcular_salario(self):
        return super().calcular_salario() + self._bono



Paso 3: Prueba del Sistema
•	Crea varios objetos de las clases Empleado y Gerente con diferentes atributos.
•	Prueba los métodos calcular_salario para asegurarte de que funcionen correctamente para ambos tipos de empleados.
•	Prueba las propiedades get y set para los atributos de los empleados.
empleado1 = Empleado("Juan", 30, 50000)
gerente1 = Gerente("Ana", 35, 60000, 10000)
 
print(empleado1.calcular_salario())  # Salida esperada: 50000
print(gerente1.calcular_salario())   # Salida esperada: 70000

Paso 4: Uso de Polimorfismo
•	Crea una función que tome un objeto Empleado como argumento y llame al método calcular_salario. Esta función debería ser capaz de manejar tanto empleados regulares como gerentes.
def calcular_y_mostrar_salario(empleado):
    print(f"El salario de {empleado.nombre} es: {empleado.calcular_salario()}")
 
empleado1 = Empleado("Juan", 30, 50000)
gerente1 = Gerente("Ana", 35, 60000, 10000)
 
calcular_y_mostrar_salario(empleado1)  # Salida esperada: El salario de Juan es: 50000
calcular_y_mostrar_salario(gerente1)   # Salida esperada: El salario de Ana es: 70000


Codigo entero: crea fichero llamado calcular_salario.py y pega el siguiente contenido
class Empleado:
    def __init__(self, nombre, edad, salario_base):
        self._nombre = nombre
        self._edad = edad
        self._salario_base = salario_base
 
    @property
    def nombre(self):
        return self._nombre
 
    @nombre.setter
    def nombre(self, nuevo_nombre):
        self._nombre = nuevo_nombre
 
    @property
    def edad(self):
        return self._edad
 
    @edad.setter
    def edad(self, nueva_edad):
        self._edad = nueva_edad
 
    @property
    def salario_base(self):
        return self._salario_base
 
    @salario_base.setter
    def salario_base(self, nuevo_salario):
        self._salario_base = nuevo_salario
 
    def calcular_salario(self):
        return self._salario_base
 
 
class Gerente(Empleado):
    def __init__(self, nombre, edad, salario_base, bono):
        super().__init__(nombre, edad, salario_base)
        self._bono = bono
 
    @property
    def bono(self):
        return self._bono
 
    @bono.setter
    def bono(self, nuevo_bono):
        self._bono = nuevo_bono
 
    def calcular_salario(self):
        return super().calcular_salario() + self._bono
 
 
def calcular_y_mostrar_salario(empleado):
    print(f"El salario de {empleado.nombre} es: {empleado.calcular_salario()}")
 
 
# Prueba del sistema
empleado1 = Empleado("Juan", 30, 50000)
gerente1 = Gerente("Ana", 35, 60000, 10000)
 
print(empleado1.calcular_salario())  # Salida esperada: 50000
print(gerente1.calcular_salario())   # Salida esperada: 70000
 
calcular_y_mostrar_salario(empleado1)  # Salida esperada: El salario de Juan es: 50000
calcular_y_mostrar_salario(gerente1)   # Salida esperada: El salario de Ana es: 70000


Paso 5: Probar el codigo:

Para probar ese codigo debes tener Python instalado en tu servidor, y ejecutar el comando 
python3 nombre_del_fichero.py

Documentacion
•	Clases y Objetos: Se definen las clases Empleado y Gerente, que son plantillas para crear objetos que representan empleados y gerentes en un sistema de gestión.
•	Atributos y Métodos en Programación Orientada a Objetos:
•	Atributos: Los atributos como nombre, edad, salario_base y bono son características de los objetos de las clases Empleado y Gerente.
•	Métodos: Se definen métodos como __init__ para inicializar los objetos, y calcular_salario para calcular el salario de los empleados y gerentes.
•	Herencia: La clase Gerente hereda de la clase Empleado, lo que significa que los gerentes tienen todos los atributos y métodos de los empleados, y además tienen atributos y métodos adicionales específicos de los gerentes.
•	Polimorfismo: Se utiliza el polimorfismo cuando se llama al método calcular_salario, ya que se comporta de manera diferente dependiendo del tipo de objeto (Empleado o Gerente) que se está utilizando.
•	Sobrecarga Dinámica de Métodos: El método calcular_salario se sobrecarga en la clase Gerente para tener en cuenta el bono adicional. Esto significa que el método se define nuevamente en la subclase Gerente con una funcionalidad diferente a la de la superclase Empleado.
•	Propiedades: Selectores (Get), Modificadores (Set) y Referencias (Let): Se utilizan propiedades con métodos get y set para los atributos de las clases Empleado y Gerente, lo que permite un acceso controlado a estos atributos y facilita la modificación de los mismos.

Paso 6: Crear aplicacion web
Utilizaremos Flask, un popular framework de Python para construir aplicaciones web, para crear una interfaz web para calcular salarios de empleados. 
1.	Crea una ec2, y habre el puerto 5000 en el grupo de seguridad de la ec2

2.	Instalar Flask si aún no lo tienes instalado. Puedes hacerlo ejecutando sudo  en tu terminal. Si no tienes pip instalado, debes instalarlo en tu servidor con yum o apt segun tu distribucion linux

3.	Crear un archivo llamado app.py y pon el siguiente código:
from flask import Flask, render_template, request
from clases import Empleado, Gerente
 
app = Flask(__name__)
 
# Ruta para el formulario de entrada de datos
@app.route('/')
def formulario():
    return render_template('formulario.html')
 
# Ruta para procesar los datos del formulario
@app.route('/calcular', methods=['POST'])
def calcular():
    nombre = request.form['nombre']
    edad = int(request.form['edad'])
    salario_base = float(request.form['salario_base'])
    tipo_empleado = request.form['tipo_empleado']
 
    if tipo_empleado == 'gerente':
        bono = float(request.form['bono'])
        empleado = Gerente(nombre, edad, salario_base, bono)
    else:
        empleado = Empleado(nombre, edad, salario_base)
 
    salario_mensual = empleado.calcular_salario_mensual()
    return render_template('resultado.html', nombre=nombre, salario=salario_mensual)
 
if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')

4.	Asegúrate de tener los archivos HTML formulario.html y resultado.html en una carpeta llamada templates en el mismo directorio que app.py.

El contenido de formulario.html:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Salario</title>
</head>
<body>
    <h1>Calculadora de Salario</h1>
    <form action="/calcular" method="post">
        <label for="nombre">Nombre:</label><br>
        <input type="text" id="nombre" name="nombre"><br>
        <label for="edad">Edad:</label><br>
        <input type="number" id="edad" name="edad"><br>
        <label for="salario_base">Salario Base:</label><br>
        <input type="number" id="salario_base" name="salario_base"><br>
        <label for="tipo_empleado">Tipo de Empleado:</label><br>
        <select id="tipo_empleado" name="tipo_empleado">
            <option value="empleado">Empleado</option>
            <option value="gerente">Gerente</option>
        </select><br>
        <label for="bono">Bono (solo para gerentes):</label><br>
        <input type="number" id="bono" name="bono" step="any" disabled><br>
        <input type="submit" value="Calcular">
    </form>
    <script>
        document.getElementById('tipo_empleado').addEventListener('change', function() {
            var bonoInput = document.getElementById('bono');
            if (this.value === 'gerente') {
                bonoInput.disabled = false;
            } else {
                bonoInput.disabled = true;
            }
        });
    </script>
</body>
</html>



Y el contenido de resultado.html:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resultado</title>
</head>
<body>
    <h1>Resultado</h1>
    <p>El salario de {{ nombre }} es: ${{ salario }}</p>
    <a href="/">Volver al formulario</a>
</body>
</html>


5.	También, necesitarás tener los archivos clases.py que contiene las clases Empleado y Gerente en el mismo directorio que app.py.

Contenido del archivo clases.py
class Empleado:
    def __init__(self, nombre, edad, salario_anual):
        self._nombre = nombre
        self._edad = edad
        self._salario_anual = salario_anual
 
    @property
    def nombre(self):
        return self._nombre
 
    @nombre.setter
    def nombre(self, nuevo_nombre):
        self._nombre = nuevo_nombre
 
    @property
    def edad(self):
        return self._edad
 
    @edad.setter
    def edad(self, nueva_edad):
        self._edad = nueva_edad
 
    @property
    def salario_anual(self):
        return self._salario_anual
 
    @salario_anual.setter
    def salario_anual(self, nuevo_salario):
        self._salario_anual = nuevo_salario
 
    def calcular_salario_mensual(self):
        return self._salario_anual / 12
 
class Gerente(Empleado):
    def __init__(self, nombre, edad, salario_anual, bono):
        super().__init__(nombre, edad, salario_anual)
        self._bono = bono
 
    @property
    def bono(self):
        return self._bono
 
    @bono.setter
    def bono(self, nuevo_bono):
        self._bono = nuevo_bono
 
    def calcular_salario_mensual(self):
        salario_base_mensual = super().calcular_salario_mensual()
        return salario_base_mensual + self._bono / 12
Una vez creados los archivos podemos deplegar nuestra aplicacion con el sigueinte comando:
python3 app.py

Accediendo a la ip de la ec2 en el servidor por el puerto 5000 deberíamos ver nuestro formulario para calcular el salario mensual
Rellena el formulario y calcula el salario, adjunta la captura de pantalla del resultado

