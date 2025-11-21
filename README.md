Ansible Monitoring Lab
Descripción

Este proyecto contiene un playbook de Ansible completo para desplegar una pila de monitorización en Linux, incluyendo:

Prometheus: para recolección y almacenamiento de métricas.

Node Exporter: para monitorizar los recursos del sistema.

Grafana: para visualización de métricas con dashboards personalizables.

MariaDB: base de datos para almacenar datos de la monitorización y usuarios de Grafana.

El objetivo es automatizar la instalación y configuración de todos estos servicios, de forma que puedan desplegarse fácilmente en cualquier servidor Linux.

Estructura del proyecto

ansible-monitoring-lab/
├── inventory                       # Inventario de Ansible
├── playbook.yml                     # Playbook principal
├── roles/
│   ├── node_exporter/
│   │   ├── tasks/main.yml
│   │   ├── templates/node_exporter.service.j2
│   │   └── files/node_exporter-1.9.1.linux-amd64.tar.gz
│   ├── prometheus/
│   │   ├── tasks/main.yml
│   │   ├── templates/prometheus.yml.j2
│   │   ├── templates/prometheus.service.j2
│   │   └── files/prometheus.tar.gz
│   ├── grafana/
│   │   ├── tasks/main.yml
│   │   └── templates/grafana.ini.j2
│   └── mariadb/
│       ├── tasks/main.yml
│       └── templates/mariadb.cnf.j2
└── README.md

Requisitos

Sistema operativo: Linux (Ubuntu, CentOS, RHEL, Fedora)

Ansible: >= 2.9

Acceso root o con privilegios sudo en los servidores.

Python 3.x en los hosts para ejecutar módulos de Ansible.

Para MariaDB, tener las credenciales de root o configuradas en /root/.my.cnf.
