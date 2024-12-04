# Install infrastructure - Data Growth Community

Repositorio del MasterClasss "Creando un ambiente de datos a prueba de balas con DevOps"

## Instituciones
- Data Growth Community - https://www.linkedin.com/company/datagrowthcommunity/
- Ayphu Cloud - https://ayphu.com/

## Tecnologias

- Ansible
- Python

### hosts file

```bash
touch hosts
```

> Content the file hosts

```bash
[services]
laboratorio ansible_host=1.2.3.4 ansible_user=root ansible_ssh_port=22
```

### Run test connection

```bash
ansible -i hosts laboratorio -m ping
```

## Install infraestructure

### 1) Package

```bash
ansible-playbook -i hosts playbook/packages.yml -e "host=laboratorio"
```

### 2) Base

```bash
ansible-playbook -i hosts playbook/base.yml  -e "host=laboratorio"
```

### 4) Upload Mysql

```bash
ansible-playbook -i hosts playbook/project.yml -e "host=laboratorio"  -e "folder=mysql"
```

> Renombrar el archivo .env_example a .env y actualizar los datos

### 5) Upload Postgres

```bash
ansible-playbook -i hosts playbook/project.yml -e "host=laboratorio"  -e "folder=postgres"
```


### 6) Upload Jupiter

```bash
ansible-playbook -i hosts playbook/project.yml -e "host=laboratorio"  -e "folder=jupiter"
```

> Renombrar el archivo .env_example a .env y actualizar los datos

### 7) Comandos basicos

| Comando                 | Descripción                                                             |
|-------------------------|-------------------------------------------------------------------------|
| docker-compose pull     | Descarga las imágenes de Docker a nuestro computador                    |
| docker-compose config   | Valida si toda la configuración está correctamente definida             |
| docker-compose up -d    | Activa los contenedores definidos en el archivo docker-compose.yml      |
| docker-compose down     | Apaga los contenedores activos                                         |
| docker ps               | Lista los contenedores que se están ejecutando                         |
| ls                      | Lista los directorios                                                  |
| pwd                     | Indica la ruta actual                                                   |

### 8) Puertos

- 1.2.3.4:8081 - PHPMyadmin
- 1.2.3.4:8082 - PGAdmin
- 1.2.3.4:8083 - Jupiter
