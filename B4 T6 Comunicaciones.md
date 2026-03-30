# FUNDAMENTOS DE TRANSMISIÓN

Las **señales analógicas** son continuas en el tiempo: su voltaje (o amplitud) varía de forma suave representando directamente la información (por ejemplo, la onda de sonido de una voz). En cambio, las **señales digitales** usan valores discretos (generalmente 0 y 1) en intervalos de tiempo fijos. Cada instante contiene un valor fijo, como “1” o “0”, y la información se codifica en secuencias de estos bits. Por ejemplo, una grabación de voz analógica tiene una forma de onda continua, mientras que en digital cada porción de esa onda se muestrea y cuantifica en números. Esto hace a la señal digital más resistente al ruido, pero requiere más ancho de banda (mayor frecuencia) para representar la misma información. De hecho, en una señal analógica cualquier magnitud (amplitud, frecuencia, fase) puede tomar infinitos valores, pero en digital sólo puede tomar uno de unos cuantos niveles predefinidos【18†L1-L5】【18†L9-L17】.

El **ancho de banda** de un medio describe su capacidad máxima para transmitir información. En sistemas analógicos se mide en Hertzios (Hz) o megahercios (MHz) y corresponde al rango de frecuencias disponibles. En canales digitales se mide en bits por segundo (bps) o sus múltiplos (Mbps, Gbps) y representa la velocidad máxima de datos teórica. Sin embargo, la **velocidad real de transferencia** suele ser menor que el ancho de banda teórico, porque los bits se empaquetan en tramas y existen pérdidas. Podríamos usar la analogía de una tubería: el ancho de banda es el diámetro del tubo (cuánto caudal cabe) y la velocidad efectiva es la presión a la que sale el agua. Como explica Disetec, *“el ancho de banda es la cantidad de información que se envía o recibe en un período”* mientras que *“la velocidad de transferencia es la rapidez con la que dos dispositivos se comunican en bit/s”*【23†L55-L59】. Por ejemplo, un enlace de fibra puede tener un ancho de banda de decenas de GHz (espectro de luz), soportando decenas de Gbps; un cable UTP Cat6a tiene ~500 MHz y 10 Gbps teóricos【36†L159-L164】; un canal de radio de 2,4 GHz (WiFi) puede alcanzar cientos de Mbps en las mejores condiciones. 

La **modulación** es el proceso de alterar una característica de una portadora (señal continua de alta frecuencia) según la señal de información. En modulación analógica, variamos la amplitud (AM), frecuencia (FM) o fase (PM) de la portadora según la señal. Por ejemplo, AM y FM en radio transmiten audio con una portadora de alrededor de 100 MHz, variando amplitud o frecuencia de la onda. En modulación digital se mapean bits a cambios discretos: ASK (Amplitude Shift Keying) cambia entre dos amplitudes; FSK (Frequency SK) entre dos frecuencias; PSK (Phase SK) varía la fase (BPSK/ QPSK con 2 o 4 estados); QAM (Quadrature AM) combina cambios de amplitud en dos vías para codificar múltiples bits por símbolo. P. ej. en modems telefónicos V.92 o en WiFi se usan técnicas QAM para lograr más bits por ciclo de señal. Cada esquema tiene compromiso entre complejidad y robustez: PSK y QAM son más eficientes (más bits por Hz) pero requieren relación señal/ruido alta.

Existe además una relación fundamental entre **frecuencia, ancho de banda y rendimiento**. Según el teorema de Shannon-Hartley, la capacidad máxima de un canal (en bps) es *C = B·log₂(1 + S/N)*, donde *B* es el ancho de banda (Hz) y *S/N* la relación señal/ruido【26†L159-L170】. Esto implica que, a mayor frecuencia disponible (B grande) y buena señal (alto SNR), mayor será la tasa de datos posible. En la práctica, bandas de radio más altas (por ejemplo, milimétricas en 5G ~30–300 GHz) permiten canales más anchos y así más Gbps, a costa de menor alcance. Por ejemplo, redes celulares 2G/GSM (900–1800 MHz) eran lentas (Kbps), mientras que 4G/LTE (1–2 GHz con agregación de portadoras) llegó a decenas de Mbps, y 5G (mmWave) promete decenas de Gbps. La misma analogía funciona en cables: un UTP Cat6a con hasta 500 MHz permite 10 Gbps a 100 m, mientras que un cable Cat5e (100 MHz) es 1 Gbps【36†L159-L164】. 

**Ejemplos prácticos:** la telefonía 1G usó modulación FM analógica (voz), 2G GSM digitalizó la voz y datos con modulación GMSK sobre 900 MHz. Un módem XDSL toma el ancho de banda del par telefónico (~5 MHz) y envía tens de Mbps dividendo la señal en múltiples sub-bandas (modulación OFDM). El WiFi 802.11ac en la banda de 5 GHz usa modulaciones QAM de hasta 1024 símbolos para alcanzar Gbps. De modo similar, las comunicaciones por radio satelital emplean QPSK o QAM optimizados a varias decenas de MHz. 

- **Resumen clave:** Las señales analógicas son continuas; las digitales discretas (bits). El ancho de banda es la capacidad disponible (Hz en analógico, bps en digital), y la velocidad real depende del esquema de modulación y ruido. Las modulaciones AM/FM/PM varían analógicamente la portadora, mientras que ASK/FSK/PSK/QAM codifican bits. Según Shannon, mayor ancho de banda y mejor SNR significan más capacidad【26†L163-L170】. P. ej., un canal de 1 MHz puro puede transmitir ~1 Mbps en condiciones ideales, pero en la práctica se usan técnicas avanzadas de codificación y multiplexación para acercarse al límite.

# MEDIOS DE TRANSMISIÓN

Los **medios cableados** más comunes son: 

- **Par trenzado (UTP/STP):** Son cables con pares de conductores enlazados. Los Cat5e admiten hasta 100 MHz (~1 Gbps a 100 m). Cat6 llega a 250 MHz (10 Gbps, pero sólo 55 m a 10G) y Cat6a hasta 500 MHz (10 Gbps a 100 m)【36†L149-L154】【36†L159-L164】. Su uso típico es en redes LAN Ethernet y cableado de oficinas.  

- **Cable coaxial:** Tiene un conductor central rodeado de blindaje. En Ethernet se usó en 10Base2 (10 Mbps a ~185 m) y 10Base5 (10 Mbps a 500 m)【51†L173-L181】【51†L194-L202】. En telecomunicaciones modernos, el coaxial de TV (750 MHz–1 GHz) se usa en cable módem (DOCSIS) que alcanza varios Gbps hoy día. Su alcance es de kilómetros en enlaces de microondas coaxiales o satélite. 

- **Fibra óptica:** Transmite luz en lugar de electricidad. Hay *monomodo* (SMF) para largas distancias (laser 1310/1550 nm, 100 km, decenas de Gbps) y *multimodo* (MMF) para distancias cortas (<500 m, 10 Gbps)【36†L159-L164】. La frecuencia óptica es del orden de 200 THz (vela a 1550 nm), permitiendo anchos de banda enormes (terabits en DWDM). Se emplea en backbones de internet, redes troncales metropolitanas, enlaces intercontinentales, o en centros de datos. 

Los **medios inalámbricos** incluyen ondas electromagnéticas de distinta frecuencia:

- **Radiofrecuencia (RF):** Abarca kHz–GHz. Por ejemplo, la radiodifusión AM/FM (100 kHz–100 MHz) o WiFi (2,4/5 GHz). Los enlaces de radio pueden ofrecer desde kbps (radio AM) hasta cientos de Mbps (WiFi 6/5G NR) dependiendo de la banda y modulación. El alcance varía: MHz bajos pueden llegar decenas de km (comunicación rural), GHz altos (WiFi) sólo decenas de metros. Uso: transmisión de señales de audio/video, redes locales inalámbricas, comunicaciones celulares, etc.

- **Microondas:** Comprende aproximadamente de 1 a 30 GHz. Ofrece canales muy anchos y se requiere línea de visión. Puede dar decenas de Mbps hasta ~10 Gbps【43†L30-L34】, con alcances de cientos de metros a decenas de km (torres repetidoras, enlaces satelitales). Se usa en enlaces punto a punto, backhaul celular, radares y comunicaciones satelitales.

- **Infrarrojo (IR):** Frecuencias de cientos de GHz a unos pocos THz (10^11–10^14 Hz). Ejemplos son sistemas IR de corto alcance (IrDA, ~1–16 Mbps a pocos metros) o mandos a distancia (baja velocidad). No penetra paredes y requiere línea de vista clara. Uso: controles remotos, enlaces de datos clase IR para dispositivos cercanos.

- **Láser (comunicaciones ópticas libres):** Ondas de luz visibles/infrarrojas coherentes (~430–800 THz). Pueden transmitir Gb/s a distancias de cientos de metros o más (enlaces ópticos inalámbricos). Suelen usarse en telecomunicaciones para enlaces terrestres punto a punto o comunicaciones satelitales láser. Requieren alineación precisa y buena visibilidad.

A continuación se muestra una tabla comparativa resumen:

| **Medio**                    | **Frecuencias típicas**     | **Velocidad**           | **Alcance típico**           | **Uso habitual**                          |
|------------------------------|----------------------------|-------------------------|------------------------------|-------------------------------------------|
| Par trenzado (Cat5e)         | ~100 MHz                   | hasta 1 Gbps            | ~100 m                       | LAN Ethernet (oficinas, hogares)          |
| Par trenzado (Cat6a)         | ~500 MHz                   | hasta 10 Gbps           | ~100 m                       | LAN de alta velocidad, data centers       |
| Coaxial (10Base2/5)          | ~10 MHz (baseband)         | 10 Mbps                | 185 m (10Base2) / 500 m (10Base5) | Ethernet antiguo, estudios de TV         |
| Coaxial (banda ancha DOCSIS) | 5–1000 MHz                 | hasta 10 Gbps           | kms                          | Cable TV, Internet por cable              |
| Fibra multimodo             | ~350 THz (850 nm LED)      | 1–10 Gbps (hasta 100)   | <500 m                       | Enlaces en campus, centros de datos       |
| Fibra monomodo              | ~193 THz (1550 nm laser)   | 10–100 Gbps (1000+)     | decenas km                   | Backbones, larga distancia                |
| Radio FM/TV                  | 30 MHz–1 GHz              | kbit/s – Mbps          | decenas km (FM)               | Radio/TV broadcast, IoT simple           |
| Celular (3G/4G/5G)          | 700 MHz–6 GHz             | hasta 1–10 Gbps         | kms (células macro)           | Telefonía móvil, datos móviles            |
| WiFi (802.11)               | 2.4/5/6 GHz               | 10 Mbps – 10 Gbps+      | decenas m                     | Redes LAN inalámbricas (casas, oficinas)  |
| Microondas punto a punto    | 1–30 GHz                  | 100 Mbps – 10 Gbps+     | 1–50 km                      | Enlaces backhaul celular, satélites       |
| Infrarrojo (IrDA)           | 300 GHz–1 THz             | hasta 16 Mbps           | <10 m                        | Controles remotos, conexión de corta distancia |
| Láser libre (FSO)           | 400–800 THz               | >1 Gbps                 | 0.1–5 km                     | Comunicaciones ópticas sin cable          |

*(Las frecuencias y velocidades son aproximadas; el rendimiento real depende del equipamiento y condiciones.)*

# ETHERNET Y ESTÁNDARES

Ethernet define varias normas de transmisión que se reconocen por nombres como 10BASE5, 10BASE-T, 100BASE-TX, 1000BASE-T, 10GBASE-T, etc. El prefijo numérico indica la velocidad (10 = 10 Mbps, 100 = 100 Mbps, 1000 = 1 Gbps, 10G = 10 Gbps); “BASE” significa señal base (sin modulación portadora extra) y la letra o número final indica el medio o topología: “5” y “2” eran coaxiales grueso/fino (10Base5 y 10Base2 a 10 Mbps sobre cable coaxial)【51†L173-L181】【53†L335-L340】, mientras que “T” (twisted pair) indica cable par trenzado. Por ejemplo, 10BASE-T usa cable Cat3 o Cat5 (10 Mbps)【53†L218-L227】, 100BASE-TX usa dos pares de Cat5 (100 Mbps a 100 MHz)【53†L247-L252】, y 1000BASE-T (Gigabit) emplea cuatro pares de Cat5e/Cat6 a 125 MHz para 1 Gbps. 10GBASE-T usa cable Cat6a o superior a 500 MHz【36†L159-L164】. Las normas Ethernet posteriores como 10GBASE-SR/LR/ER son sobre fibra óptica (en longitudes de onda de 850/1310/1550 nm) soportando 10 Gbps. 

Entre sí mantienen compatibilidad descendente: un enlace 10/100/1000 se adapta dinámicamente a la máxima velocidad posible【49†L502-L509】. Como ilustración, transferir 10 GB toma ~2h13m a 10BASE-T (10 Mbps) pero sólo 8 s a 10GBASE-T (10 Gbps)【49†L502-L509】. 

A continuación, una tabla ejemplifica estándares típicos:

| **Estándar**    | **Velocidad** | **Medio físico**             | **Frecuencia aproximada**      |
|-----------------|--------------|-----------------------------|-------------------------------|
| 10BASE5         | 10 Mbps      | Cable coaxial grueso        | ~10 MHz (baseband)【51†L194-L202】 |
| 10BASE2         | 10 Mbps      | Cable coaxial fino (RG-58)  | ~10 MHz (baseband)【51†L173-L181】 |
| 10BASE-T        | 10 Mbps      | Par trenzado Cat3/5         | ~10 MHz【53†L218-L227】       |
| 100BASE-TX      | 100 Mbps     | Par trenzado Cat5 (2 pares) | 31.25 MHz (MLT-3 codif.)【53†L247-L252】 |
| 1000BASE-T      | 1 Gbps       | Par trenzado Cat5e/6 (4 pares) | 125 MHz (PAM-5 codif.)     |
| 10GBASE-T       | 10 Gbps      | Par trenzado Cat6a (4 pares) | 500 MHz【36†L159-L164】      |
| 100BASE-FX      | 100 Mbps     | Fibra óptica multimodo (2 fibras) | 62.5 MHz (850 nm)     |
| 1000BASE-SX     | 1 Gbps       | Fibra multimodo (850 nm)    | - (óptico)                   |
| 10GBASE-SR      | 10 Gbps      | Fibra multimodo (850 nm)    | -                           |

Estos estándares muestran cómo a mayor velocidad suelen usarse cables de mayor categoría (y frecuencias más altas)【36†L159-L164】【49†L502-L509】.

- **Resumen clave:** Ethernet evolucionó de 10 Mbps coaxial (10BASE2/5) a 100 Mbps (Fast Ethernet) y 1–10 Gbps (Gigabit/TenGigabit Ethernet). Cada estándar (IEEE 802.3) indica la velocidad y medio: p.ej. “10GBASE-T” = 10 Gigabit Ethernet sobre par trenzado a 500 MHz【36†L159-L164】. Los equipos negocian la mejor velocidad disponible según la calidad del cable【49†L502-L509】. 

# MODOS DE TRANSMISIÓN

Un canal de comunicación puede operar en varios modos de transmisión:

- **Simplex:** Sólo se transmite en una dirección (un emisor, un receptor). El flujo va de un punto A a B y nunca al revés. Ejemplos clásicos: la radiodifusión de radio o TV (la emisora transmite, los radios/TV sólo reciben), o la señal de un sensor que envía datos a un procesador sin recibir comandos. En el modo simplex no hay “conversación”: sólo unidireccional【56†L1412-L1420】.

- **Half-Duplex (semidúplex):** Permite comunicación en ambas direcciones, pero no al mismo tiempo. Cuando un lado transmite, el otro sólo recibe; luego se invierten los roles. Ejemplo común: los *walkie-talkies*, donde uno habla (“transmite”) mientras el otro escucha, y luego cambian. En redes, las Ethernet con hubs antiguos (colisión CSMA/CD) funcionaban en semi-dúplex: un nodo transmitía y sólo cuando terminaba podían otros usar el medio. El modo half-duplex ahorra cables (basta uno) pero baja la eficiencia en datos simultáneos【56†L1445-L1453】【56†L1458-L1461】.

- **Full-Duplex (dúplex completo):** Permite transmitir y recibir simultáneamente. Cada extremo tiene un canal de transmisión independiente. Ejemplos: una llamada telefónica permite hablar y escuchar al mismo tiempo. En las redes, la mayoría de switches modernos y enlaces punto a punto (p. ej. líneas de fibra óptica, switches Gigabit) operan en full-dúplex, duplicando efectivamente la capacidad. Como señala QSFPTek, el full-duplex *“es una versión mejorada del semidúplex”* con comunicación simultánea en ambos sentidos【56†L1481-L1490】.

Una buena analogía: un simplex es como un altavoz dando un discurso a un público (solo salidas); el half-duplex es un walkie-talkie (“comienzo/fin” para hablar); el full-duplex es una llamada de teléfono simultánea【56†L1481-L1490】. 

- **Resumen clave:** En modo simplex sólo fluye un solo sentido (p. ej. emisión de radio)【56†L1412-L1420】; en half-duplex cada parte puede enviar, pero uno a la vez (p. ej. walkie-talkie)【56†L1445-L1453】; en full-duplex ambos se comunican simultáneamente (p. ej. teléfono)【56†L1481-L1490】. Las redes modernas (Ethernet con switches) suelen usar full-duplex para máxima eficiencia. 

# TIPOS DE ENVÍO EN RED

Cuando hablamos de direcciones y envío de datos en redes, existen cuatro modos principales:

- **Unicast:** comunicación uno a uno. Un paquete se dirige a una única dirección de destino. Es el modo más común: toda conexión TCP/IP típica (navegar, correo, ping a una IP específica) es unicast. Ejemplo: enviar un correo de A a B, el paquete IP va de la IP origen a la IP destino, sin ser entregado a otros nodos【60†L267-L274】. Analogía: una carta dirigida a un amigo【60†L275-L278】.

- **Broadcast:** comunicación uno a todos en un dominio. El emisor envía un solo paquete que debe ser recibido por *todos* los dispositivos en la red local. Usos típicos: ARP Request en IPv4 (cada máquina de la LAN consulta quién tiene una IP) o DHCP Discover. Por ejemplo, hacer `ping 192.168.1.255` envía un broadcast a todas las PCs de la subred【60†L279-L287】. Analogia: hablar por altavoz en una plaza para que todos lo escuchen【60†L289-L291】.

- **Multicast:** comunicación uno a un grupo de suscriptores. El paquete se envía a una dirección grupal especial; sólo los dispositivos que se han unido a ese grupo (suscriptores) lo reciben. Es útil para ahorrar tráfico cuando hay muchos receptores interesados en un contenido, pero no todos. Ejemplos prácticos: un canal de streaming en vivo donde sólo quienes sintonizan reciben el video. El servidor emite una sola copia, y solo los usuarios suscritos al grupo multicast la reciben【60†L293-L301】. (En Internet global no se usa mucho, pero en redes IPTV o videoconferencias puede usarse IGMP/Multicast). Analogía: un boletín de barrio enviado solo a suscriptores interesados【60†L303-L306】.

- **Anycast:** comunicación uno al “más cercano” o “mejor” receptor. Varias máquinas comparten la misma dirección IP; la red envía el paquete al nodo topológicamente más cercano (o más rápido). El ejemplo más famoso: los servidores de DNS públicos (8.8.8.8 de Google, 1.1.1.1 de Cloudflare) usan anycast. Cuando accedes a 8.8.8.8, tu consulta se dirige automáticamente al servidor DNS de Google geográficamente o topológicamente más cercano, reduciendo latencia【60†L307-L317】. Otra aplicación: balanceo global de contenidos. Analogía: llamar al número central de una cadena de tiendas, que te conecta con la sucursal más cercana【60†L319-L322】.

- **Ejemplos concretos:** En Internet normal (navegar web, correo) todo es unicast. En redes LAN domésticas, el envío de un archivo a la impresora es unicast. Cuando tu PC solicita una IP nueva o resolución DNS en IPv4, usa broadcast (DHCP/ARP). Un stream de video corporativo puede emplear multicast. Los servicios DNS públicos usan anycast para enviar tus consultas al mejor servidor global【60†L309-L317】.

- **Resumen clave:** Unicast es punto a punto (1→1)【60†L269-L274】. Broadcast es 1→todos en el segmento (ej. ARP)【60†L279-L287】. Multicast es 1→grupo suscrito (ej. streaming a grupos)【60†L293-L301】. Anycast es 1→el más cercano (ej. DNS global 8.8.8.8)【60†L307-L317】. 

# CONMUTACIÓN Y DIFUSIÓN

Las redes pueden operar con varios métodos de **conmutación**:

- **Conmutación de circuitos:** se establece un canal dedicado antes de la comunicación, reservando recursos fijos durante toda la sesión【65†L146-L154】. Es como realizar una llamada telefónica por la red telefónica conmutada: una vez establecida, parece un cable virtual continuo. Ejemplo clásico: la RTC (Red Telefónica Conmutada)【65†L169-L174】. En redes antiguas digitales conmutadas (ISDN) también se usó. Ventaja: latencia constante, secuencia ordenada. Desventaja: ineficiente para datos burst (si la línea está vacía, se desperdicia). Requiere fases de establecimiento y desconexión del circuito【65†L155-L164】.

- **Conmutación de paquetes:** divide los datos en paquetes independientes que se envían por la red según demandan【63†L169-L178】. Cada paquete contiene dirección, y puede seguir rutas distintas. Los nodos (routers o switches) almacenan y reenvían paquetes (store-and-forward). Esto es la base de Internet: no hay camino dedicado, sino que los enlaces se comparten estadísticamente entre flujos de diferentes usuarios【63†L186-L194】. Ventaja: utiliza eficientemente los enlaces (multiplexación estadística), múltiples conversaciones paralelas sin reservar canal fijo【63†L186-L194】. Ejemplo: enviar un email, solicitar un sitio web. Desventaja: puede haber retrasos o pérdidas si la red se satura (cada paquete compite por el enlace).

- **Conmutación de mensajes:** es un método intermedio y más antiguo en que cada mensaje completo (no dividido) se almacena enteramente en cada nodo y luego se reenvía. Era usado en redes pre-Internet (por ejemplo, la antigua red telegráfica o de pedidos). Los nodos “almacenan y reenvían” mensajes completos, lo que puede introducir gran latencia, pero tolera mejor errores (porque se reenvía el mensaje completo si falla).

En cuanto a **redes de difusión**, se refiere a medios donde un envío de datos se propaga a todos los nodos. Por ejemplo, un hub Ethernet o un enlace coaxial antiguamente: un paquete transmitido llegaba a **todos** los puertos y cada dispositivo decide si procesarlo. El broadcast de Ethernet es un caso de difusión (todos lo reciben). En radiocomunicaciones, una emisora AM hace difusión total del aire. 

Históricamente, la telefonía (conmutación de circuitos) dominaba hasta 1980–90. Con el surgimiento de ARPANET en 1969 se impulsó la conmutación de paquetes. Luego las LAN con hubs eran “difusión”: todo escuchaba todo (colisiones CSMA/CD). Después evolucionaron a redes “conmutadas” (switches), donde los paquetes van solo al destino específico (efecto similar a conmutación de paquetes eficiente). 

- **Comparativa:** La conmutación de circuitos brinda calidad constante pero poca flexibilidad (p. ej. no es óptima para datos intermitentes)【65†L146-L154】. La conmutación de paquetes maximiza el uso del canal y adapta la ruta dinámicamente (Internet)【63†L169-L178】【63†L186-L194】. La difusión envía a todos, útil para mensajes globales (ARP, anuncios) pero ineficiente si hay muchos nodos. Las redes modernas prefieren paquetes conmutados y eliminan la mayoría de los ancestros de difusión (solo se usa en broadcast control).

- **Resumen clave:**  
  - *Conmutación de circuitos:* canal fijo dedicado (teléfono)【65†L146-L154】.  
  - *Conmutación de paquetes:* datos divididos en paquetes independientes (Internet)【63†L169-L178】.  
  - *Conmutación de mensajes:* mensaje completo almacenado y reenvío en cada nodo (antiquo).  
  - *Redes de difusión:* medio compartido donde todos reciben las transmisiones (LANs con hubs, radio).  
  Las redes actuales usan casi siempre conmutación de paquetes, reservando difusión solo para casos puntuales de broadcast local.

# DISPOSITIVOS DE RED (SEGÚN OSI)

| **Dispositivo**      | **Capa OSI**       | **Función principal**                                                |
|----------------------|--------------------|---------------------------------------------------------------------|
| **DTE** (Equipo Terminal de Datos) | – (Capa 1 del usuario) | Equipo final que origina o consume datos (PC, impresora, sensor). No es elemento de interconexión; simplemente inicio/final de comunicación. |
| **Repetidor**        | Capa 1 (Física)    | Refuerza y regenera señales eléctricas/ópticas. Une dos tramos de cable prolongando distancia, sin ninguna inteligencia. |
| **Hub (concentrador)** | Capa 1 (Física)    | Multi-puerto repetidor. Recibe señal en un puerto y la reenvía a todos los demás. Opera en semidúplex; crea dominio de colisión único【71†L133-L141】. |
| **Bridge (puente)**  | Capa 2 (Enlace)    | Filtra y reenvía tramas Ethernet según dirección MAC. Conecta segmentos LAN; no crea dominio de colisión, solo reenvía lo necesario. |
| **Switch (conmutador)** | Capa 2 (Enlace)    | Evolución del puente con múltiples puertos. Aprende direcciones MAC y envía cada trama sólo al puerto destino. Algunos switches L3 soportan routing básico. |
| **Router**           | Capa 3 (Red)       | Conecta diferentes redes IP. Lee direcciones IP de paquete, elige la mejor ruta y reencamina paquetes entre subredes. |
| **Gateway (pasarela)** | Capa 4–7 (varía)   | Traduce entre distintos protocolos o modelos de red (p.ej. entre una LAN y la red telefónica o entre SMTP e X400). Es un término genérico para convertidores de protocolo complejos (a veces firewalls o VOIP gateways). |
| **Proxy (servidor proxy)** | Capa 7 (Aplicación) | Intermedia entre clientes y servidores en capa de aplicación. P. ej. un proxy HTTP recibe peticiones web, las reenvía y devuelve contenido, aplicando filtros o caching. |
| **Cortafuegos (Firewall)** | Capa 3–7         | Filtra paquetes o conexiones según reglas de seguridad. En la capa 3/4 controla direcciones IP y puertos; en capas superiores puede inspeccionar protocolos (HTTP, DNS, etc.) para bloquear contenido indeseado. |
| **Punto de acceso inalámbrico (AP)** | Capa 2 / 1      | Actúa como bridge/repetidor para redes Wi-Fi. Permite a dispositivos Wi-Fi conectarse a una LAN cableada, puenteando las tramas inalámbricas a puertos Ethernet. Opera en la capa física y de enlace. |

Según la guía de IONOS, por ejemplo, un **hub** es un dispositivo de capa física (1) que simplemente retransmite bits a todos los puertos【71†L133-L141】. Un **switch** se considera capa 2 porque procesa tramas Ethernet por MAC. Un **router** opera en capa 3, encaminando paquetes IP entre redes. Un **bridge** también es capa 2, separa dominios de colisión. Un **gateway** típico de Internet (NAT/router de frontera) opera en capas 3–4; un **proxy** en capa 7; un **firewall** puede abarcar 3–7 según su sofisticación. 

- **Resumen clave:** Dispositivos de capa 1/2 (repetidores, hubs) solo regeneran señales, sin filtrar; de capa 2 (bridges, switches) manejan direcciones MAC y tramas; de capa 3 (routers) manejan direcciones IP; pasarelas/proxies/firewalls suelen actuar en capas altas (4–7) realizando traducciones o filtrados avanzados【53†L335-L340】【71†L133-L141】. Un punto de acceso Wi-Fi es un puente inalámbrico (capa física/enlace) para dispositivos móviles.

# TIPOS DE REDES Y TOPOLOGÍAS

**Escalas de red (por alcance):** 

- **PAN (Personal Area Network):** Red de área personal, suele ser inalámbrica (Bluetooth, ZigBee, etc.) con alcance ~10 m. Conecta dispositivos cercanos al usuario (teléfono, reloj, auriculares).  
- **LAN (Local Area Network):** Red de área local, abarca una zona pequeña (edificio, oficina). Suelen ser cableadas (Ethernet) o Wi-Fi. Velocidades altas (Mbps–Gbps) y latencia baja. Ej.: LAN de casa o de una empresa【74†L51-L60】.  
- **MAN (Metropolitan Area Network):** Abarca una ciudad o campus universitario【74†L69-L78】. Une varias LAN con enlaces de fibra o microondas. Velocidades moderadas (o altas) y distancias intermedias.  
- **WAN (Wide Area Network):** Cubre regiones, países o continentes【74†L87-L95】. Conecta múltiples LAN/MAN mediante enlaces públicos (internet, satélite, MPLS). Latencias y distancias mayores; velocidad baja respecto a LAN. Ej.: Internet es la mayor WAN global.  
- **SAN (Storage Area Network):** Red especializada dedicada al almacenamiento masivo empresarial【91†L159-L168】. No es LAN/WAN de usuarios, sino infraestructura de datos (FibreChannel, iSCSI) para conectar servidores con grandes matrices de disco. Alta velocidad y disponibilidad (¡horas de terabytes!)【91†L172-L179】. Se usa en centros de datos y entornos corporativos.

**Topologías físicas:** determinan cómo se conectan los nodos:

- **Bus:** Todos los nodos se conectan a un único cable troncal. Ventaja: simple y económico (un solo cable comparte todos)【77†L107-L113】. Inconveniente: si falla el cable central, la red entera cae; las señales se atenúan con la distancia; y ante muchas estaciones surgen colisiones (se usa contienda CSMA/CD). Ej. Ethernet coaxial original (10Base2).  
- **Estrella:** Todos los nodos se conectan a un nodo central (hub o switch). Ventajas: si un enlace falla, sólo se pierde ese nodo, el resto sigue; fácil de expandir y localizar fallas. Cada enlace es individual, lo que elimina colisiones (en switches) y simplifica el cableado (N cables para N nodos)【77†L84-L92】. Desventajas: el nodo central es punto único de fallo; más cableado total que bus; necesita dispositivo activo (hub/switch).  
- **Anillo:** Cada nodo conecta con dos vecinos formando un círculo. Los datos circulan en una sola dirección (o doble anillo en ambos sentidos). Ventaja: en teoría evita colisiones (token passing), cada nodo reenvía de forma ordenada. Inconveniente: si cualquier enlace se rompe, el anillo se interrumpe por completo; añadir nodos es más complejo. Ej. Token Ring de IBM. Hoy casi en desuso.  
- **Malla:** Cada nodo se conecta directamente con todos los demás (full mesh) o con varios vecinos (partial mesh). Ventaja: alta redundancia y fiabilidad; hay múltiples rutas entre puntos【77†L59-L64】. Inconveniente: mucho cable/costes; complejo de configurar. Se usa donde la fiabilidad es crítica (enlaces backbone, redes ad hoc militares, torres celulares en pequeña escala).  
- **Árbol (Jerárquica):** Es una combinación de varias topologías de estrella unidas en forma de árbol. Ventajas: escalable y fácil de organizar en niveles (sucursales → datacenter). Permite dividir red en segmentos. Inconveniente: las divisiones superiores son puntos de congestión; la falla de un segmento troncal puede aislar ramas enteras.

La siguiente tabla resume ventajas e inconvenientes:

| **Topología** | **Ventajas**                                   | **Desventajas**                                          |
|--------------|-----------------------------------------------|----------------------------------------------------------|
| **Bus**      | Requiere poco cable (uno solo); fácil de instalar.| Todo depende del cable central: si falla, la red cae; escasa tolerancia a fallos; colisiones frecuentes (red no fiable para muchos nodos).【77†L107-L113】 |
| **Estrella** | Aisla fallos individuales: un cable dañado solo afecta a un nodo; fácil añadir dispositivos; detecta fácilmente fallas. No hay colisiones si se usa switch. 【77†L84-L92】| Requiere más cable total; nodo central es único punto crítico (si falla, la red entera cae); costo del concentrador. |
| **Anillo**   | Acceso ordenado (token), evita colisiones; buen aprovechamiento del canal. | Un solo fallo en el anillo interrumpe toda la red; difícil expansión; latencia aumenta con muchos nodos. |
| **Malla**    | Gran redundancia (múltiples rutas), muy fiable【77†L59-L64】; escasa congestión. | Costo muy alto de cable/puertos; complejidad de instalación y gestión; se suele usar full mesh solo en redes pequeñas o esenciales. |
| **Árbol**    | Escalable (combina estrellas), distribuye el tráfico; estructura jerárquica clara. | Puntos críticos en nodos intermedios; latencia mayor que estrella simple; requiere planificación. |

- **Resumen clave:** Las redes se clasifican por alcance: PAN (dev. personales), LAN (hogar/empresa), MAN (ciudad), WAN (mundo)【74†L51-L60】【74†L69-L78】. SAN es una red dedicada de almacenamiento de alto rendimiento【91†L159-L168】. En topologías, el bus es simple pero frágil, la estrella es robusta pero centralizada, la malla es la más fiable pero costosa, y el anillo es ordenado pero susceptible a fallos de un solo punto【77†L107-L113】【77†L84-L92】. Cada topología se elige según tamaño, costo y requisitos de confiabilidad.

# VPN Y REDES PRIVADAS

Una **VPN (Red Privada Virtual)** extiende de forma segura una red privada sobre una pública (Internet). Funciona creando un **túnel cifrado** entre el cliente y la red de la empresa: todo el tráfico que pasa por este túnel queda protegido y parece venir desde la red corporativa【80†L205-L213】. En la práctica, un dispositivo del lado del usuario (software VPN o cliente) establece túnel hacia un **gateway VPN** en la empresa. De este modo, el empleado remoto accede a recursos internos (ficheros, servidores) como si estuviera físicamente conectado. La VPN garantiza confidencialidad y autenticación mutua (solo usuarios autorizados)【80†L176-L184】.

Existen dos modos básicos de VPN:

- **VPN de acceso remoto:** Conecta un solo equipo (o pocos) remoto con la red corporativa. Por ejemplo, un trabajador en casa se conecta al gateway de la oficina con un cliente VPN (IPsec o SSL/TLS). Esto protege su conexión doméstica, impidiendo que terceras partes intercepten los datos empresariales【80†L213-L222】. Requiere un servidor/gateway VPN en la oficina y software cliente en cada equipo remoto. Este es el caso típico de teletrabajo.

- **VPN Site-to-Site:** Conecta redes completas entre sí. Por ejemplo, la sucursal de Madrid se conecta a la sede central de Barcelona mediante un túnel VPN fijo entre sus routers. Así, las redes LAN de ambas sedes se comportan como si estuvieran físicamente unidas. Es transparente para los usuarios y útil para oficinas remotas o colaboraciones entre empresas【80†L213-L222】. Puede ser de intranet (dentro misma empresa) o extranet (entre empresas colaboradoras)【80†L213-L222】.

Un punto importante es el **túnel completo vs. dividido**:

- **Túnel completo (full-tunnel):** Todo el tráfico del cliente se envía por la VPN. Esto maximiza la seguridad (todo va cifrado por el túnel), pero puede congestionar el enlace y aumentar latencia, ya que incluso datos de Internet genéricos pasan por el gateway corporativo.  
- **Túnel dividido (split-tunneling):** Solo parte del tráfico (p. ej. el destinado a la red corporativa) viaja por el VPN. El resto (servicios generales de Internet) sale directamente desde la conexión local del usuario. Así se mejora el rendimiento y se ahorra ancho de banda en la VPN【83†L491-L500】. Sin embargo, el tráfico “fuera del túnel” no está cifrado por la VPN, por lo que esta opción se emplea con cuidado. En resumen: *full-tunnel=todo por VPN (seguro pero más lento), split-tunnel=solo lo esencial por VPN (más rápido, menos carga)【83†L491-L500】*.

**Ejemplo práctico:** Un empleado X trabajando desde casa usa su portátil y ejecuta una VPN corporativa (IPsec). Al iniciar la sesión VPN, su PC recibe una IP interna de la empresa y puede acceder a servidores de archivos, intranet, etc. Si la empresa activa túnel completo, toda navegación web del empleado saldrá cifrada por la VPN (p. ej. páginas de la intranet y de Internet). Con túnel dividido, solo las solicitudes a direcciones internas van por el túnel; navegar por Facebook, por ejemplo, pasaría directo por su conexión de casa. El portal Cibernos destaca que las VPN de acceso remoto “salvaguardan la comunicación entre dispositivos de la empresa y del trabajador”【80†L219-L224】, y menciona que en teletrabajo han sido clave para extender la red corporativa de forma segura【80†L205-L213】.

- **Resumen clave:** Una VPN crea un **túnel cifrado** seguro a través de Internet【80†L205-L213】. Puede ser *acceso remoto* (cliente individual a oficina) o *site-to-site* (sucursales conectadas)【80†L213-L222】. En modo **full-tunnel**, todo el tráfico pasa por el VPN (más seguro, pero puede enlentecer), mientras que en **split-tunneling** solo pasa por el túnel el tráfico sensible (se mantienen otros accesos locales)【83†L491-L500】. Las empresas usan VPN para teletrabajo y conexiones interoficinas, garantizando confidencialidad y autenticación【80†L176-L184】【80†L213-L222】. 

# COMUNICACIONES MÓVILES E INALÁMBRICAS

**Evolución 1G→5G:** Las generaciones móviles se han ido sucediendo con avances tecnológicos:  
- **1G** (años 80): analógico (p.ej. sistema AMPS), solo voz.  
- **2G** (años 90): redes digitales (GSM, CDMA) – introducen SMS y datos muy lentos (GPRS ~50–100 kbps, EDGE ~200 kbps). GSM usa modulación GMSK/TDMA en 900–1800 MHz.  
- **3G** (2000s): introducen datos multimedia (UMTS 384 kbps–2 Mbps, luego HSPA hasta ~14 Mbps). Usaban WCDMA/OFDM en 2100 MHz.  
- **4G LTE** (2010s): puro IP y modulaciones avanzadas (OFDMA, MIMO). LTE logró decenas de Mbps reales (teóricos 150 Mbps downlink) y LTE Advanced superó 100–300 Mbps【85†L169-L177】. Opera entre 700 MHz–3.5 GHz, con agregación de portadoras.  
- **5G** (2020s): principios de IP avanzadas y ondas mmWave (24–90 GHz) para muy alta velocidad y baja latencia. Teóricamente hasta decenas de Gbps【85†L177-L185】 (p.ej. antenas 5G NSA/SA en 3.5 GHz logran cientos de Mbps; en mmWave se anuncian 10–20 Gbps). Además prioriza masiva conectividad IoT (mMTC) y ultra-fiable baja latencia (URLLC) para aplicaciones críticas.

**Arquitectura GSM vs LTE:** GSM (2G) era una red de conmutación de circuitos/datos muy estructurada: los datos pasaban por una red de conmutación centralizada (MSC, BSC, BTS). LTE (4G) es completamente basada en IP, con arquitectura plana: las señales se manejan por enrutadores e IP; no hay conmutación de circuito. LTE emplea OFDM para mayor eficiencia espectral, antenas MIMO para multiplicar velocidad, y redes de paquetes (EPC) en lugar de MSC.

**Wi-Fi:** Son estándares de LAN inalámbrica (IEEE 802.11) que operan típicamente en bandas de 2.4 GHz y 5 GHz (y nuevas en 6 GHz para WiFi6E). Las versiones claves son:
- 802.11a/b/g/n (hasta 600 Mbps, MIMO),  
- 802.11ac (WiFi 5, varias decenas de Mbps hasta ~3.5 Gbps combinados en 80–160 MHz con múltiples antenas),  
- **802.11ax (WiFi 6):** OFDMA, 1024-QAM, hasta ~9.6 Gbps en total【83†L491-L500】, mejor eficiencia en entornos saturados.  
- **802.11be (WiFi 7, en desarrollo):** Aún mayor (teórico ~30–40 Gbps) usando canales de 320 MHz y QAM de orden superior.  
Wi-Fi se usa en hogares, oficinas, hotspots; cada nuevo estándar ofrece más velocidad y capacidad para IoT y streaming.

**Bluetooth:** Red inalámbrica PAN de corto alcance (~2.4 GHz, ISM). Versión 5.0 en adelante puede alcanzar ~2 Mbps (LE) o mayor, alcance ~50–100 m en clase 1. Ideal para periféricos (auriculares, ratones), IoT de baja potencia (sensores), manos libres, etc. Opera en capa física similar al Wi-Fi pero con protocolos distintos (piconets).

**Tecnologías actuales destacadas:**
- **5G móvil:** Además de gran velocidad en frecuencias altas, integra celdas pequeñas (micro/pico-celdas), Massive MIMO, beamforming. Soporta IoT masivo (mMTC) y baja latencia para AR/VR o automóviles (URLLC). El uso de bandas bajas (600 MHz) da cobertura amplia con 100+ Mbps.  
- **WiFi 6 y 6E:** Mejoran rendimiento en ambientes concurridos (OFDMA, TWT). WiFi 7 promete aún más ancho de banda (p.ej. hasta 46 Gbps según Spectrum) y latencias muy bajas.  
- **IoT/LPWAN:** Surgen redes de área amplia de baja potencia. Ejemplos: **LoRaWAN** y **Sigfox** (ISM sin licencia, 0.3–50 kbps, decenas de km alcance) o **NB-IoT/LTE-M** (espectro licenciado de celulares, ~200 kbps a bajo consumo)【89†L264-L268】. Estas permiten conectar miles de sensores con baterías que duran años (seguimiento de activos, medidores inteligentes, agricultura). Por ejemplo, LoRaWAN opera a 125 kHz en bandas libres y ofrece hasta ~50 kbps【89†L264-L268】, ideal para datos pequeños. NB-IoT en red celular puede alcanzar ~200 kbps【89†L264-L268】. Estas tecnologías complementan a WiFi/Bluetooth y 5G para el crecimiento del IoT masivo.

- **Resumen clave:** Las generaciones celulares avanzaron de 1G analógico (voz) a 5G (datos ultrarrápidos, IoT). GSM 2G y LTE 4G son arquitecturas muy distintas: GSM usa circuitos y conmutación; LTE es todo IP/OFDM con antenas MIMO. Wi-Fi (802.11) evoluciona hoy a WiFi 6/7 para mayores velocidades en 2.4/5/6 GHz. Bluetooth provee PANs cortas 2.4 GHz. Tecnologías recientes de IoT (LPWAN) como LoRa o NB-IoT permiten gran conectividad de sensores a largo alcance y baja potencia【89†L264-L268】. Cada avance sigue la demanda de más velocidad, más dispositivos y menor consumo.

