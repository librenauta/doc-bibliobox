---
description: Inicio de guía de instalación de Bibliobox
---

# doc-bibliobox

Paso a paso

1.- Montar un servidor.

2.- Crear una biblioteca



Primeros apuntes del pad:



- puntos claves para inicio.  
-  
--lista de bibliotecas hogareñas- [http://181.231.168.244/](http://181.231.168.244/)  
  
[https://bibliobox.copiona.com/posts/biblio-box.html](https://bibliobox.copiona.com/posts/biblio-box.html), si lo pones en modo dark se ve que seleccionas, tengo que arreglar esto a futuro..  
instalacion de 0  
---------------------------------------------------------------------usar si no tenes monitor y teclado  
[https://zinenauta.copiona.com/img/Z5-3-min.png](https://zinenauta.copiona.com/img/Z5-3-min.png)  
  
&gt;use la recomendación de la web de raspi para instalar la imagen en una sdluego en la particion boot cree un archivo llamado "ssh" en una terminal parado en la memoria y en el directorio boot: $ y luego la conecte a mi router para pegarle desde mi pc a ssh pi@laipquesaquedelrouter y entrar a la raspi  
-  
- nmap   
--&gt; usar nmap para saber que ip asignó el router a la raspi  
 nmap -sn 192.168.0.0/100 or nmap -sn 192.168.1.0/100 luego  passwr : raspberry o raspberrypi  
---------------------------------------------------------------------  
&gt;instalamos una servidora web, esto quiere decir: el programa que se ejecutará constantemente para poder brindar acceso a determinadas carpetas en nuestra computadora.nginx es el nombre del programa.  
 luego de update-upgrade instalar nginx:          en raspbian \(como es una distribución de debian para raspi\) instalamos cosas con esta sentencia en una terminal: sudo \(para brindar permisos de modificacion de sistema\) apt install \(comando para instalar\) nginx \(programa a instalar\) php-fpm \(instalar php\)         pi@raspberry:$ sudo apt install nginx php-fpm  
para la bibliobox \(biblioteca virtual\) necesitamos configurar la placa de wifi de la raspberrypi en modo Acces point, \(las placas de wifi tienen 2 modos, cliente o punto de acceso, esto quiere decir que o se puede conectar como clinete a un router o puede crear una red de wifi autonoma\)  
Comenzamos a Configurar el Acces Point:          sudo apt-get install dnsmasq hostapd          sudo systemctl stop dnsmasq     sudo systemctl stop hostapd  
  
&gt;instalando hostapd y dnsmask desde [https://thepi.io/how-to-use-your-raspberry-pi-as-a-wireless-access-point/](https://thepi.io/how-to-use-your-raspberry-pi-as-a-wireless-access-point/)  
editar static ip sudo nano /etc/dhcpcd.conf  
  
interface wlan0 static ip\_address=192.168.100.1/24 nohook wpa\_supplicant  
sudo service dhcpcd restart  
  
  
si hostapd tira error al iniciar:    sudo systemctl unmask hostapdsudo systemctl enable hostapdsudo systemctl start hostapd  
  


