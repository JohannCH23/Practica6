<h3> #Practica 5 - Johan Erazo </h3>

<h2> Engade ó docker-compose do DNS outro servizo (container) que faga a función de cliente. </h2>

Comezamos editando o arquivo .yml do DNS, engadindo o novo servizo de cliente cunha imaxe base de Ubuntu.
O arquivo .yml estará no repositorio na carpeta compostest subido.

Onde definín os dous servizos de DNS (o servidor e o cliente), configurei o cliente para que dependa do DNS.

Configurei o DNS do cliente para que poida usar o servizo.
<h2> Instala, se é preciso, os paquetes que precises para usar no cliente os comandos de rede do seguinte enlace. </h2>

Para instalar o que precisa o cliente faise primeiro un (apt-get update) xunto con (apt-get install dnsutils).
<h2> Comproba o seu uso </h2>

Para comprobalo lanza o (docker compose up -d) e, ao lanzalo en segundo plano, poderás facer consultas na mesma terminal.
<h2> Configura o cliente para que o seu DNS sexa o outro contedor, modificando o resolv.conf ou usando o ficheiro docker-compose.yml (preferible) </h2>

Para configuralo, o que fixen foi engadir en Networks a subnet e o driver en bridge, para que se conecte ao contedor, un config coa subnet, o rango de IPs e a súa gateway.
<h2> Compróbao con 'dig'. </h2>

Agora facemos a comprobación dentro do contedor usando (docker exec -it N1cliente sh). Así entraremos e executaremos o "dig" para a comprobación, que se faría da seguinte maneira: (dig @172.28.5.1 exemplo.asircastelao.inet).