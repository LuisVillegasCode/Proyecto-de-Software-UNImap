# UNIMap

UNIMap es una herramienta académica desarrollada en Python para apoyar el análisis inicial de conectividad y exposición de servicios dentro de una red controlada. Integra Nmap para descubrir hosts y puertos, clasifica los servicios detectados mediante una base de reglas y genera reportes que facilitan la revisión de hallazgos.

El proyecto fue desarrollado como parte del curso de Programación Orientada a Objetos de la Facultad de Ingeniería Eléctrica y Electrónica de la Universidad Nacional de Ingeniería.

## Funcionalidades

- Descubrimiento de hosts activos mediante Nmap.
- Escaneo de puertos y servicios expuestos.
- Clasificación inicial de riesgos a partir de reglas definidas en una base JSON.
- Recomendaciones de mitigación asociadas a los servicios identificados.
- Generación de reportes en formatos HTML, CSV y TXT.
- Envío opcional de reportes por correo electrónico.
- Interfaz web sencilla construida con Flask.

## Alcance

UNIMap no reemplaza una plataforma profesional de gestión de vulnerabilidades. La identificación de riesgos se basa en una base de reglas mantenida dentro del proyecto y no realiza, por sí sola, correlación automática con fuentes como NVD, CPE, CVE o feeds de inteligencia de amenazas.

Su propósito es demostrar un flujo básico de descubrimiento de activos, identificación de servicios, clasificación de riesgo y generación de reportes.

## Requisitos

- Python 3
- Nmap instalado en el sistema
- Dependencias de Python incluidas en `requirements.txt`

Instalación de dependencias:

```bash
pip install -r requirements.txt
```

Nmap debe instalarse por separado desde su distribución oficial y estar disponible en la variable `PATH` del sistema.

## Configuración

El módulo de notificaciones utiliza variables de entorno para evitar almacenar credenciales dentro del código.

Crea un archivo `.env` local o configura las variables directamente en el sistema:

```text
GMAIL_USER=correo_ejemplo@gmail.com
GMAIL_APP_PASSWORD=tu_contrasena_de_aplicacion
```

El archivo `.env` está excluido del control de versiones. El repositorio incluye `.env.example` únicamente como referencia.

## Ejecución

Desde la carpeta `UNImap`:

```bash
python app.py
```

La aplicación inicia un servidor Flask desde el cual se puede ingresar el rango de red, seleccionar el tipo de análisis y consultar el reporte generado.

## Flujo general

```text
Rango de red
    |
    v
Descubrimiento / escaneo con Nmap
    |
    v
Identificación de servicios
    |
    v
Clasificación mediante reglas
    |
    v
Reporte HTML / CSV / TXT
    |
    v
Notificación opcional por correo
```

## Uso responsable

El escaneo de redes debe realizarse únicamente sobre infraestructura propia o sobre entornos para los que se cuente con autorización expresa.

## Autores

- Zahid Franschesco Palomino Pimpinco
- Luis Javier Villegas Noblecilla
- Fatima Lizeth Toscano Velasquez
- Adrian Mayta Nuñez
