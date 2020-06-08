Kebutuhan :
1. Installed Docker Machine
2. Virtualbox

Langkah
1. Buat docker-machine jumlah sessuai dengan node yang di inginkan
`docker-machine create --driver virtualbox "name of machine"` Pastikan  `docker-machine ls`
2. lihat ip (ifconfig) kemudian jadikan sebagai leader
`docker swarm init –advertise-addr 192.168.99.1`
3. lihat token untuk join dalam docker swarm
`docker swarm join-token worker` bisa di update untuk jdi manager , worker tidak bisa akses untuk mengontrol swarm -> jika ingin meng update `docker node update --role manager node2`
`docker swarm join-token manager`
4. Masukan token ke masing-masing node dengan perintah
`docker-machine ssh node2` kemudian copy paste token dari leader
5. Coba untuk membuat service 3 replika
`docker service create --replicas 3 alpine ping 8.8.8.8`
