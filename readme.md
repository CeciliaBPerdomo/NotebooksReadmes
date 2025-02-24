# 📒 Notebooks: Un Solo Ambiente de Trabajo
## 📌 ¿Qué es un Notebook y Cómo Funciona?
Un **notebook** (como Jupyter Notebook o Google Colab) es un entorno interactivo donde puedes escribir y ejecutar código en **celdas**.

A diferencia de los archivos de código tradicionales (`.py` en Python, por ejemplo), donde todo el código se ejecuta de arriba hacia abajo en un solo archivo, en un notebook **puedes ejecutar diferentes partes del código en distintos momentos y en cualquier orden**.

Sin embargo, todas las celdas comparten la misma **memoria** y el mismo **estado**.

## 🔹 Importaciones y Variables en Notebooks
Cuando ejecutas una celda en un notebook, el código dentro de esa celda **se ejecuta y se guarda en la memoria**. Esto significa que si defines una variable o importas una librería en una celda, podrás usarla en otra celda sin necesidad de repetir la importación o definición.

### ✍ Ejemplo de Importaciones
En una celda, podemos importar una librería como `math`:
``` python
import math  # Importamos la librería math
``` 

Luego, en otra celda diferente, podemos usar `math.sqrt()`, aunque no hayamos vuelto a escribir `import math`:
``` python
print(math.sqrt(25))  # Funciona porque math ya está importado en la memoria
``` 

## ❌ Error Común: Ejecutar Celdas en el Orden Incorrecto
Si intentamos usar algo antes de ejecutarlo, obtendremos un error.
### 🔻 Error típico:
``` python
print(math.sqrt(25))  # ERROR: math no está importado aún
``` 

### 🔺 Solución
Primero ejecutamos la celda donde importamos `math`, luego ejecutamos la celda con `print(math.sqrt(25))`.

### 💡 Regla Clave
El código que ejecutas en una celda queda disponible en todo el notebook, pero solo después de ejecutarlo.

🛠 Ejercicio Paso a Paso
Sigue estos pasos para comprender mejor cómo funciona el notebook:
1️⃣ En la primera celda, importa la librería random:
import random

2️⃣ En la segunda celda, genera un número aleatorio usando random.randint(1, 10):
numero = random.randint(1, 10)
print("Número aleatorio:", numero)

3️⃣ Ejecuta la segunda celda sin haber ejecutado la primera. ¿Qué pasa?
4️⃣ Ahora ejecuta la primera celda y luego vuelve a ejecutar la segunda.
✅ Conclusión:
Si ejecutas una celda con una importación o una variable, esta queda guardada en la memoria del notebook.
Puedes usar lo que definiste en cualquier otra celda, siempre y cuando hayas ejecutado la celda que lo definía primero.
Si cierras el notebook o reinicias el kernel, perderás todo lo que estaba en la memoria y tendrás que volver a ejecutar las celdas necesarias.
📌 Resumen Final: Un notebook es un solo ambiente de trabajo donde todas las celdas comparten memoria, pero debes ejecutarlas en el orden correcto para que funcionen correctamente. 🚀


🎓 Google Colab: Recursos Limitados y Alternativas
📌 ¿Qué es Google Colab?
Google Colab (o Google Colaboratory) es un entorno de notebooks en la nube que te permite ejecutar código en Python sin necesidad de instalar nada en tu computadora. Es ideal para aprender, experimentar y realizar proyectos pequeños o medianos con acceso gratuito a GPUs y TPUs.
Sin embargo, Colab tiene recursos limitados, lo que significa que:
✔ No puedes usar todo el poder de una supercomputadora.
✔ El tiempo de ejecución de las máquinas es limitado.
✔ Puede desconectarte automáticamente si estás inactivo o consumes demasiada memoria.

🔴 Limitaciones de Google Colab
1️⃣ RAM y CPU Limitadas
En la versión gratuita, obtienes alrededor de 12 GB de RAM y una CPU virtual moderada.
Si consumes demasiada memoria, el notebook se puede reiniciar y perderás todo lo que no hayas guardado.
2️⃣ Tiempo de Ejecución Máximo
Las sesiones en Google Colab no son permanentes.
Si dejas de usar el notebook por un tiempo o ejecutas procesos largos, Google puede cerrarlo automáticamente.
3️⃣ Acceso Restringido a GPU y TPU
Puedes usar una GPU para acelerar cálculos con TensorFlow o PyTorch, pero no es garantizado que siempre tengas acceso.
Si muchas personas están usando Colab al mismo tiempo, podrías no obtener una GPU disponible.
Para ver si tienes GPU activada, usa este comando en una celda:


!nvidia-smi


4️⃣ Pérdida de Datos si Reinicias el Entorno
Si el entorno se desconecta o se reinicia, todo lo que estaba en la memoria (variables, modelos, archivos temporales) se pierde.
Para evitar esto, guarda tus archivos importantes en Google Drive o descárgalos a tu máquina.

✅ Soluciones y Alternativas
🔹 Guardar Archivos en Google Drive
Para evitar perder archivos cuando se reinicia Colab, puedes conectarlo a tu Google Drive:
from google.colab import drive
drive.mount('/content/drive')

🔹 Trabajar en Tu Propia Computadora
Si necesitas más recursos o tiempo ilimitado, considera instalar Jupyter Notebook o usar un entorno local como Anaconda.
📌 Pasos para instalar Jupyter Notebook en tu PC:
1️⃣ Descarga e instala Anaconda desde https://www.anaconda.com/.
2️⃣ Abre Anaconda y ejecuta:
jupyter notebook

3️⃣ Se abrirá tu navegador con un entorno similar a Google Colab, pero usando los recursos de tu PC.
🔹 Google Colab Pro (Opcional, pero de Pago)
Si necesitas más RAM o acceso garantizado a GPUs, Google ofrece Colab Pro (de pago), que te da mejores recursos y más tiempo de ejecución.

🔥 Conclusión
💡 Google Colab es excelente para pruebas rápidas y proyectos pequeños, pero si necesitas más poder de cómputo, lo mejor es trabajar en tu propia computadora o en servidores más potentes. 🚀
📝 VS Code Notebooks: Programación Interactiva en tu Computadora
📌 ¿Qué es un Notebook en VS Code?
Un VS Code Notebook es un tipo especial de archivo (.ipynb) que permite ejecutar código en celdas, similar a Jupyter Notebook o Google Colab. La diferencia principal es que todo se ejecuta en tu propia computadora, lo que significa que tienes control total sobre los recursos y el tiempo de ejecución.
✅ Ventajas de usar notebooks en VS Code:
Puedes ejecutar código en celdas individuales sin correr todo el script.
No dependes de internet ni de Google Colab.
Puedes usar todo el poder de tu computadora (más RAM, CPU, y GPU si tienes una).
Se integra con extensiones de Python y Jupyter en VS Code.

🛠 Cómo Usar Notebooks en VS Code
🔹 1. Instalación de los Requisitos
Para usar notebooks en VS Code, necesitas instalar algunas herramientas:
1️⃣ Instalar VS Code
Descárgalo desde https://code.visualstudio.com/
2️⃣ Instalar la Extensión de Python
Abre VS Code
Ve a la pestaña Extensiones (Ctrl + Shift + X)
Busca Python e instálala.
3️⃣ Instalar Jupyter en Python
Si no lo tienes instalado, abre una terminal en VS Code y ejecuta:
pip install jupyter


🔹 2. Creando un Notebook en VS Code
1️⃣ Abre VS Code.
2️⃣ Ve a Archivo > Nuevo Archivo y guarda el archivo con extensión .ipynb.
3️⃣ Verás un entorno similar a Jupyter con celdas de código.
4️⃣ Escribe código en una celda y ejecútalo con el botón ▶️ o presionando Shift + Enter.

🖥 Ejemplo Básico en VS Code Notebooks
🔹 Celda 1: Importar Librerías
import math

🔹 Celda 2: Usar la librería importada
print(math.sqrt(36))  # Output: 6.0

💡 Recuerda: Al igual que en Jupyter o Colab, las celdas comparten memoria, por lo que puedes definir una variable en una celda y usarla en otra.

⚡ Diferencias Clave entre VS Code Notebooks y Google Colab
Característica
VS Code Notebooks 🖥
Google Colab ☁️
Ubicación
Computadora local
Nube de Google
Recursos
Sin límites, depende de tu PC
Limitados
Conexión a Internet
No es necesaria
Necesaria
Acceso a GPU
Si tienes GPU, puedes usarla con CUDA
Depende de disponibilidad
Tiempo de Ejecución
Ilimitado
Puede desconectarse


🎯 Conclusión
📌 VS Code Notebooks te da más control sobre tus recursos y no tiene las limitaciones de la nube. Si trabajas en proyectos grandes o necesitas más potencia, es una mejor opción que Google Colab.
✅ Recomendación: Si vas a trabajar con notebooks a largo plazo, instala VS Code y Jupyter en tu computadora para evitar las restricciones de Google Colab. 🚀

