<h1 align="center">Arquitectura de Redes</h1>

<p align="center">
  <strong>Interconexión de cuatro sistemas autónomos mediante BGP</strong><br>
  OSPF · RIPv1 · RIPv2 · VLAN · ACL · Wi-Fi
</p>

<p align="center">
  Isabel Alonso Casas<br>
  Universidad Pontificia Comillas · ICAI<br>
  Práctica final de Arquitectura de Redes · Abril de 2026
</p>

<p align="center">
  <a href="memoria-redes.pdf"><strong>Leer la memoria completa (PDF)</strong></a>
  ·
  <a href="practica_definitiva.pkt"><strong>Archivo de Cisco Packet Tracer</strong></a>
</p>

## Descripción

Proyecto académico de diseño, configuración y documentación de una infraestructura formada por **cuatro sistemas autónomos (AS)**. Cada dominio utiliza un protocolo de encaminamiento interno diferente y se conecta con los demás mediante **BGP externo (eBGP)**.

La práctica integra planificación del direccionamiento IPv4, segmentación mediante VLAN, encaminamiento entre redes, agregación de rutas, conectividad inalámbrica y filtrado de tráfico mediante listas de control de acceso.

## Topología general

![Topología general de los cuatro sistemas autónomos](docs/topologia-general.png)

*Diagrama original incluido en la memoria del proyecto.*

Las vecindades entre sistemas autónomos son **A–B, A–C, B–C y C–D**. El AS C actúa como punto de tránsito para alcanzar el AS D desde A y B.

## Sistemas autónomos

| Sistema | Encaminamiento interno | Elementos principales |
| --- | --- | --- |
| **AS A** | OSPF, área 0 | Cuatro VLAN departamentales, Router-on-a-Stick, enlaces internos y ACL para limitar la salida del Departamento 1 a servicios web. |
| **AS B** | RIPv1 | Red empresarial con routers en anillo, subredes de tamaño uniforme y filtrado de entrada que permite HTTP y Telnet. |
| **AS C** | RIPv2 | LAN públicas, enlaces internos privados, red Wi-Fi con DHCP y desactivación de la sumarización automática. |
| **AS D** | Rutas estáticas | Router frontera, router interno y una interfaz loopback que representa la red `221.0.0.0/16`. |


## Archivos del repositorio

| Archivo o carpeta | Contenido |
| --- | --- |
| [`practica_definitiva.pkt`](practica_definitiva.pkt) | Archivo de trabajo de Cisco Packet Tracer. |
| [`memoria-redes.pdf`](memoria-redes.pdf) | Memoria original de 52 páginas: requisitos, diseño, direccionamiento, implementación, verificaciones y configuraciones de los dispositivos. |
| [`docs/`](docs/) | Diagramas de la topología general y de cada AS, extraídos de la memoria. |


## Diagramas por sistema autónomo

<details>
<summary>AS A · OSPF y VLAN</summary>

![Topología del AS A](docs/as-a.png)

</details>

<details>
<summary>AS B · RIPv1 y filtrado</summary>

![Topología del AS B](docs/as-b.png)

</details>

<details>
<summary>AS C · RIPv2 y Wi-Fi</summary>

![Topología del AS C](docs/as-c.png)

</details>

<details>
<summary>AS D · Rutas estáticas y loopback</summary>

![Topología del AS D](docs/as-d.png)

</details>

## Autoría

**Isabel Alonso Casas** · Universidad Pontificia Comillas, ICAI.

Práctica final de Arquitectura de Redes, presentada el **24 de abril de 2026**.
