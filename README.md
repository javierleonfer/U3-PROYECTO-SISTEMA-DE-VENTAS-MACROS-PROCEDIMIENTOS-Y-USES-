# U3-SISTEMA-DE-VENTAS-MACROS-PROCEDIMIENTOS-Y-USES-
# FACILITADOR: DR.MEDINA.
# DOCUMENTACION DE LEON FERNANDEZ ALEXIS JAVIER 8-9HRS.

RETROALIMENTACION DEL PROYECTO U2 ...RECICLANDO LINEAS DE CODIGO IMPLEMENTANDO MACROS...
#Para estar en contexto la version anterior hemos puesto un archivo binario INV1 y seguridad implementada mediante proto/invoke ..ahora se ha optado por guardarlo en un archivo txt para facilitación de lectura 
¿Qué cambió en la Unidad 3?
Procedimientos: las tareas que se repetían quedaron en un solo procedimiento. Por ejemplo, AskValidated pide un dato hasta que sea válido, AskProductQuantity busca el producto y pide la cantidad para recibir y vender, y FindCode busca productos.
Macros: las instrucciones cortas que se repetían ahora son macros, como mPrint para mostrar mensajes, mJmpOutOfRange para validar rangos y mRetOK/mRetError para regresar con éxito o error. mReportCF usa LOCAL porque tiene etiquetas internas.
USES: cada procedimiento guarda solo los registros que modifica. Los registros que regresan un resultado, como EAX, quedan fuera de USES.
Archivo en texto: el inventario ahora se guarda en inventario.txt y se puede abrir con el Bloc de notas:
ESP-032|185.50|10|ESP32 DevKit
RES-220|1.25|4|Resistencia 220 ohm
LED-005|2.50|30|LED rojo 5 mm
Archivos
Archivo	Contenido
Proyecto_Electronica/main.asm	Código principal y procedimientos
Proyecto_Electronica/MacrosVentas.inc	Macros del sistema
Proyecto_Electronica/Electronica.inc	Constantes y estructura Product
inventario.txt	Inventario de prueba
datos_prueba/	Inventario de ejemplo y un archivo inválido para pruebas
REPORTE_U3.docx	Reporte con la sección "Versión de la Unidad 3"
version_unidad2/	Código de la Unidad 2 para comparar
Cómo compilar y ejecutar
Tener Visual Studio 2022 con Desarrollo para el escritorio con C++ y la biblioteca Irvine en C:\Irvine\Irvine. Si Irvine está en otra carpeta, cambia <IrvineDir> en Proyecto_Electronica.vcxproj.
Abrir Proyecto_Electronica.sln.
Elegir Debug y x86.
Compilar → Recompilar solución.
Ejecutar con Ctrl + F5.

El programa lee y guarda inventario.txt en la carpeta principal del proyecto. Para empezar de nuevo, copia datos_prueba/inventario_ejemplo.txt sobre inventario.txt.
