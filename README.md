Esqueleto para comezar un proxecto con bind9

1. Instala o servidor BIND9 no equipo darthvader. Comproba que xa funciona coma servidor DNS caché pegando no documento de entrega a saída deste comando dig @localhost www.edu.xunta.es

![Imagen 1](img/1.png)

2. Configura o servidor BIND9 para que empregue como reenviador 8.8.8.8. pegando no documento de entrega contido do ficheiro /etc/bind/named.conf.options e a saída deste comando: dig @localhost www.mecd.gob.es.

![Imagen named.conf.options](img/named.conf.options.png)
![Imagen 2](img/2.png)

3. Instala unha zona primaria de resolución directa chamada "starwars.lan" e engade os seguintes rexistros de recursos (a maiores dos rexistros NS e SOA imprescindibles):

![Imagen named.conf.local](img/named.conf.local.png)
![Imagen DB.STARWARS.LAN](img/DB.STARWARS.LAN.png)
![Imagen 3](img/3.png)


4. Instala unha zona de resolución inversa que teña que ver co enderezo do equipo darthvader, e engade rexistros PTR para os rexistros tipo A do exercicio anterior. Pega no documento de entrega o contido do arquivo de zona, e do arquivo /etc/bind/named.conf.local.

![Imagen named.conf.local2](img/named.conf.local2.png)
![Imagen db.inversa](img/db.inversa.png)

5. Comproba que podes resolver os distintos rexistros de recursos. Pega no documento de entrega a saída dos comandos:

nslookup darthvader.starwars.lan localhost

![Imagen 4](img/4.png)

nslookup skywalker.starwars.lan localhost

![Imagen 5](img/5.png)

nslookup starwars.lan localhost

![Imagen 6](img/6.png)

nslookup -q=mx starwars.lan localhost

![Imagen 7](img/7.png)

nslookup -q=ns starwars.lan localhost

![Imagen 8](img/8.png)

nslookup -q=soa starwars.lan localhost

![Imagen 9](img/9.png)

nslookup -q=txt lenda.starwars.lan localhost

![Imagen 10](img/10.png)

nslookup 192.168.20.11 localhost

![Imagen 11](img/11.png)