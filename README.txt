Nombres del equipo:
- Isabella Tulcán
- Luis Eduardo Zaldumbide
- Martin Ruiz

Contribuciones:
- Isabella Tulcán: Desarrollo principal del shell en Java. Implementación del ciclo principal de ejecución, parsing de comandos ingresados por el usuario y separación de argumentos. Implementación de comandos internos (cd, pwd, history, exit). Manejo de ejecución de comandos externos utilizando ProcessBuilder. Implementación de secuencias en primer plano (=>) y validaciones para evitar errores en la ejecución (por ejemplo, impedir exit en segundo plano). Pruebas funcionales y corrección de errores detectados durante la integración.

- Luis Eduardo Zaldumbide: Apoyo en la lógica del procesamiento de comandos y validación de entradas. Implementación y pruebas del operador de ejecución en segundo plano (^^). Manejo de control de procesos (espera de procesos en foreground y no bloqueo en background). Mejora en el manejo de errores para comandos inválidos o mal formados. Pruebas de casos límite (comandos vacíos, múltiples operadores, combinaciones inválidas) y ajustes para asegurar un comportamiento estable del shell.

- Martin Ruiz: Integración Docker (Dockerfile, estructura de carpetas/archivos, iproute2).

Comentarios/observaciones:
- Repositorio GitHub: https://github.com/miatulcan/JavaShell
- Imagen Docker: miatulcan/jsh:javashell
- Comandos usados para publicar la imagen:
  docker tag jsh miatulcan/jsh:javashell
  docker push miatulcan/jsh:javashell

Pasos para abrir y ejecutar el trabajo (asumiendo solo Git y Docker instalados):
1) Clonar el repositorio:
   git clone https://github.com/miatulcan/JavaShell
   cd JavaShell

2) Construir la imagen localmente (desde Dockerfile):
   docker build -t miatulcan/jsh:javashell .

3) Ejecutar el contenedor:
   docker run -it --rm miatulcan/jsh:javashell

4) Probar dentro del shell:
   - Ver prompt con ruta actual: jsh:/ruta>>
   - Probar builtins: pwd, cd /folder1, history, exit
   - Probar comandos externos: ls, echo "hola mundo", ip addr, sleep 1, date
   - Probar secuencia en primer plano: echo hola => sleep 1 => date
   - Probar background: sleep 3 ^^ echo "bg" ^^
   - Probar exit

Opcional (si prefiere descargar imagen ya publicada):
   docker pull miatulcan/jsh:javashell
   docker run -it --rm miatulcan/jsh:javashell


