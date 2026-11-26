# Laboratorio 15 — Pruebas de rendimiento

**Curso:** Construcción y Pruebas de Software  
**Modalidad:** Individual  
**Aplicación base:** [jgomezz/petclinic_load_test](https://github.com/jgomezz/petclinic_load_test)  
**Guía:** GLAB-S15-JFARFAN-2026-02

## Objetivo

Preparar PetClinic para ejecutarse en un servidor, diseñar un plan de pruebas de carga con Apache JMeter, ejecutar diferentes niveles de concurrencia y analizar los resultados.

## Plan de trabajo

### 1. Preparación del proyecto
- [ ] Revisar y obtener el proyecto base del curso.
- [ ] Revisar el perfil Maven `prod` y `application-prod.yml`.
- [ ] Configurar la conexión a MySQL para producción sin publicar contraseñas ni llaves.
- [ ] Generar `petclinic.jar` localmente con Maven y guardar la salida del comando.

### 2. Preparación del servidor
- [ ] Definir si se reutilizará una instancia EC2 disponible o si se solicitará una nueva.
- [ ] Preparar Ubuntu, JDK, MySQL, esquema y datos.
- [ ] Desplegar el JAR y verificar `GET /pets`.
- [ ] Configurar Nginx como proxy hacia la aplicación y comprobar el acceso HTTP.
- [ ] Registrar las reglas de red necesarias y retirar las que ya no se necesiten al terminar.

### 3. Plan de JMeter
- [ ] Crear el plan `TestPlan` con grupo de hilos, configuración HTTP, petición y aserción.
- [ ] Añadir los listeners de resultados solicitados en la guía.
- [ ] Guardar el plan JMeter (`.jmx`) en esta carpeta.
- [ ] Ejecutar cargas con 10, 100, 1000 y 5000 usuarios/hilos, subida de 10 segundos y una iteración, según la guía.
- [ ] Comprobar el consumo del servidor con `top`.
- [ ] Evaluar el modo no gráfico de JMeter para las ejecuciones de carga.

### 4. Resultados y entrega
- [ ] Guardar los resultados originales de JMeter y el reporte HTML generado.
- [ ] Comparar tiempos de respuesta, tasa de errores y comportamiento del servidor entre cargas.
- [ ] Incluir capturas auténticas de configuración, ejecución y resultados.
- [ ] Redactar tres conclusiones basadas en los datos observados.
- [ ] Revisar que no se hayan incluido contraseñas, archivos `.pem` ni credenciales en el repositorio.

## Estructura prevista

```text
Laboratorio 15/
├── README.md
├── jmeter/
│   └── TestPlan.jmx
├── resultados/
│   ├── csv/
│   └── reportes/
└── evidencias/
```

Los resultados y evidencias se agregarán conforme se ejecute cada etapa. La guía marca como adicionales la búsqueda de usuario y la revisión de logs; se registrarán solo si se realizan.

## Nota sobre AWS

La preparación del repositorio y del plan JMeter puede avanzar sin crear recursos en AWS. El despliegue y la ejecución de carga contra EC2 se harán cuando se confirme qué instancia se utilizará. No se guardarán claves privadas ni contraseñas en GitHub.
