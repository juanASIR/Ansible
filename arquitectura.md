## *Arquitectura y Componentes*
![arquitectura](https://www.silcom.com.pe/images/ansible2.png)

La arquitectura de Ansible se basa en un enfoque de agenteless (sin agente) y utiliza un modelo de comunicación push (empuje). A continuación, se describen los componentes clave de la arquitectura de Ansible:

1. **Control Node (Nodo de Control)**:

El nodo de control es la máquina desde la cual se ejecuta Ansible. Aquí, se almacenan los playbooks (scripts de automatización escritos en YAML) que describen las tareas a realizar en los nodos gestionados. El control node necesita tener Ansible instalado y acceso a la red para comunicarse con los nodos gestionados.

2. **Inventario (Inventory)**:
   
Ansible utiliza un archivo de inventario para definir los nodos gestionados y agruparlos en categorías. Puede ser un archivo estático o dinámico, y se utiliza para especificar información como las direcciones IP, nombres de host, y las variables específicas de cada nodo.

3. **Módulos (Modules)**:

Los módulos son pequeños programas que Ansible ejecuta en los nodos gestionados para realizar tareas específicas. Cada módulo es responsable de una funcionalidad particular (instalar un paquete, copiar archivos, reiniciar un servicio, etc.).

Ansible cuenta con una amplia biblioteca de módulos incorporados, y también es posible desarrollar módulos personalizados.

4. **Playbooks**:
   
Los playbooks son archivos escritos en YAML que definen las tareas y roles a ejecutar en los nodos gestionados. Un playbook puede contener múltiples plays, y cada play consiste en una serie de tareas asociadas a un grupo específico de nodos.

Los playbooks describen el estado deseado del sistema y Ansible se encarga de llevar los nodos a ese estado.

5. **SSH (Secure Shell)**:
   
Ansible utiliza SSH para conectarse a los nodos gestionados y ejecutar los módulos y tareas definidas en los playbooks. Es necesario que los nodos gestionados tengan configurado el acceso SSH para permitir la conexión desde el nodo de control.

6. **Facts (Hechos)**:

Ansible recopila información sobre los nodos gestionados, como el sistema operativo, la arquitectura del hardware, las interfaces de red, etc. Estos detalles se almacenan en variables llamadas "facts".

Los facts pueden utilizarse en los playbooks para tomar decisiones basadas en la información del sistema.

7. **Roles**:

Son conjuntos de ficheros y tareas parecidos sobre un determinado grupo de hosts. Algunos de los roles más habituales son el webserver, el nginx o el dbserver. 

8. **Files**:

Es el directorio donde se almacenan los ficheros que queremos copiar en los hosts que pertenecen a un determinado rol.

9. **Task**:

Es el fichero del directorio donde definimos las tareas que queremos ejecutar en los hosts que pertenecen a ese determinado rol. El objetivo de cada tarea es ejecutar un módulo, y debe contar con un “name” que será incluido a la hora de programar la operación. 

