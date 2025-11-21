# Ansible Monitoring Lab

## Descripción
Este proyecto es un laboratorio completo de monitorización usando **Ansible** para desplegar una stack de monitoreo con **Prometheus**, **Node Exporter**, **Grafana** y **MariaDB** en sistemas Linux.  
El objetivo es automatizar la instalación, configuración y puesta en marcha de todos los servicios, permitiendo reproducir un entorno de monitorización funcional de manera rápida y sencilla.

---

## Características
- Despliegue automatizado de Node Exporter para monitorizar métricas del sistema.
- Instalación y configuración de Prometheus con scrapes para Node Exporter.
- Configuración de Grafana para visualización de métricas.
- MariaDB para almacenar credenciales y datos necesarios para Grafana.
- Servicios gestionados mediante **systemd**.
- Todos los archivos y binarios necesarios incluidos en el repositorio para pruebas locales.

---

## Estructura del proyecto

```text
ansible-monitoring-lab/
├── inventory                    # Inventario de Ansible
├── playbook.yml                 # Playbook principal
├── roles/
│   ├── node_exporter/
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   ├── templates/
│   │   │   └── node_exporter.service.j2
│   │   └── files/
│   │       └── node_exporter-1.9.1.linux-amd64.tar.gz
│   ├── prometheus/
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   ├── templates/
│   │   │   ├── prometheus.yml.j2
│   │   │   └── prometheus.service.j2
│   │   └── files/
│   │       └── prometheus.tar.gz
│   ├── grafana/
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   └── templates/
│   │       └── grafana.ini.j2
│   └── mariadb/
│       ├── tasks/
│       │   └── main.yml
│       └── templates/
│           └── mariadb.cnf.j2
└── README.md
````

---

## Requisitos

- **Sistema operativo**: Linux (Ubuntu, CentOS, RHEL, Fedora)
- **Ansible**: >= 2.9
- **Acceso root** o con privilegios sudo en los servidores
- **Python 3.x** en los hosts para ejecutar los módulos de Ansible
- Para **MariaDB**, tener las credenciales de root configuradas en `/root/.my.cnf` o conocer el usuario y contraseña

---


