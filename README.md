# Proyecto-Infraestructura-en-red--redes-2026
🏢 Proyecto: Infraestructura de Red – Redes2026

Diseño e implementación de una arquitectura de red corporativa en Cisco Packet Tracer, basada en un edificio de 3 pisos, aplicando principios de switching, direccionamiento IP y acceso remoto seguro mediante SSH.

🧠 Objetivos
Implementar una red LAN segmentada en múltiples pisos
Configurar dispositivos de capa 1, 2 y 3 del modelo OSI
Asignar direccionamiento IP coherente
Verificar comunicación entre dispositivos
Implementar acceso remoto seguro (SSH)

🏗️ Topología de Red
🔹 Primer Piso
1 Switch Cisco 2960
6 Teléfonos IP
6 PCs conectados a teléfonos
1 Impresora en red
1 MCU conectada a:
Aire acondicionado
Alarma

🔹 Segundo Piso
1 Switch Cisco 2960
1 Router inalámbrico
5 Laptops conectadas vía WiFi
1 Impresora
1 MCU conectada a:
Aire acondicionado
Termostato

🔹 Tercer Piso
1 Switch Cisco 2960
1 Router Cisco 1941
1 Firewall ASA 5505
1 Nube (Internet)
5 servidores:
DHCP
DNS
WEB
MAIL
TFTP
1 MCU conectada a:
Cámara
Aire acondicionado
Termostato

🌐 Direccionamiento IP

Segmento utilizado:

172.20.X.0/24

Ejemplo:

Gateway: 172.20.31.1
PCs: 172.20.31.2 - 172.20.31.254
Máscara: 255.255.255.0

Router:

G0/0 → 172.20.31.1
G0/1 → 200.200.31.1
🔐 Configuración de Seguridad (SSH)

Configuración aplicada en el router:

hostname BRITANNY
ip domain-name labrana.cl

username admin1 secret cisco-admin1
enable secret cisco-ena

crypto key generate rsa
2048

ip ssh version 2
ip ssh time-out 60
ip ssh authentication-retries 3

line vty 0 4
 login local
 transport input ssh
 
🧪 Pruebas realizadas
✔️ Conectividad
Ping entre dispositivos del mismo piso ✔️
Ping hacia gateway ✔️
✔️ Acceso remoto
ssh -l admin1 172.20.31.1

Resultado:

Solicita usuario y contraseña ✔️
Acceso exitoso al router ✔️
⚠️ Problemas encontrados (y soluciones)
🔴 Problema: SSH no respondía
Causa: modo Simulation activado
Solución: cambiar a Realtime
🔴 Problema: comando no funcionaba
Causa: modo incorrecto (config-line)
Solución: salir a modo privilegiado (#)
🔴 Problema: conexión fallaba
Causa: topología / enlaces entre switches
Solución: reconexión y verificación de puertos
📸 Evidencia (agregar imágenes)
Topología de red
Ping exitoso
SSH funcionando
Configuración del router
🧠 Conclusión

Se logró implementar una red funcional en un entorno simulado, aplicando conceptos de:

Switching
Direccionamiento IP
Interconexión de dispositivos
Seguridad mediante SSH
Troubleshooting de red
🚀 Tecnologías utilizadas
Cisco Packet Tracer
Modelo OSI
IPv4
SSH
