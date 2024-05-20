# Ansible Kubernetes Cluster
![Kubernetes Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/200px-Kubernetes_logo_without_workmark.svg.png)

Este repositorio contiene un conjunto de playbooks de Ansible para automatizar la instalación y configuración de un clúster de Kubernetes.

## Requisitos

- [Ansible](https://www.ansible.com/) instalado en el equipo desde el cual se ejecutarán los playbooks.
- Sistema operativo admitidos:
    - Centos 9

## Instalación

1. Clona este repositorio en tu máquina local:

    ```bash
    git clone https://github.com/Alopezfu/kubernets_cluster.git
    ```

2. Modifica el archivo `inventory` para incluir las direcciones IP o nombres de host de tus máquinas y ajusta cualquier otra configuración necesaria en formato JSON.

3. Ejecuta el playbook principal para instalar el clúster de Kubernetes:

    ansible-playbook main.yml -i inventory

## Nota
### Fallo al crear el clúster
En caso de necesitar restablecer la configuraciópn de kubernetes para relanzar el el proceso hemos de ejecutar lo siguente:

    kubeadm reset -f && rm -rf $HOME/.kube
    
Esto dejara la maquina libre de las configuraciones hechas por pos playbooks, y de esta manera poder relanzar el proceso.

## Obtener join command
Para obtener el comando para añadir nodos al clúster usamos:

    kubeadm token create --print-join-command


## Uso

Una vez que la instalación haya finalizado correctamente, tendrás un clúster de Kubernetes listo para usar. Puedes verificar el estado del clúster y comenzar a desplegar tus aplicaciones y servicios.

## Contribución

Las contribuciones son bienvenidas. Si encuentras algún problema o tienes una idea para mejorar este proyecto, por favor, abre un issue o envía un pull request.