# Kubernetes
1. Memulai kubernetes

`#minikube start`

`#minikube status`

2. Melihat nodes

`#kubectl get nodes`

3. Membuat pod

`#kubectl create -f nginx.yaml` nama pod unix jika membuat sama maka namespace harus dibedakan (dlm file yml, penambahan label)

4. Membaut pod dengan namespace

`#kubectl create -f finance-namespace.yaml` buat dulu namespace nya.

`#kubectl create -f nginx.yaml --namespace namanamespace` nama namespace dalam file yaml.

`#kubectl label pods namapod key=value` kalo misal tambah label langsung `#kubectl annotate pods namapod key="value"` kalo misal tambah annotation langsung. Keduanya kalo mau ditimpa tinggl kasi `--overwrite`

5. Melihat pod

`#kubectl get pods`

`#kubectl describe pods namapod`

`#kukectl get pods --show-label`

`#kukectl get pods -l key` atau `key=value` atau `#kubectl get pod --show-label -l key`

`#kubectl get namespace `

`#kubectl get pods --namespace namanamespace`

6. Membuat replicationcontroller

`#kubectl create -f nginx-rc.yaml` fungsi replicationcontroller adh menjaga jumlah replika pod, agar pod selalu berjumlah trsebut.

7. Melihat replicationcontroller

`#kubectl get replicationcontroller` atau `#kubectl get rc` setelah itu cek pod nya ada berapa.

8. Membuat replicaset

`#kubectl create -f nginx-rs.yaml` lebih dianjurkan dri pada replikacontroller

9. Melihat replicaset

`#kubectl get replicaset` atau ``#kubectl get rs` setelah itu cek pod nya ada berapa.

6. Menghapus

`#kubectl delete namespace namanamespace`

`#kubectl delete pod namapod` atau kalo mau berdasarkan label `#kubectl delete pod -l key=value` atau kalau berdasarkan namespace `#kubectl delete pod --all --namespace namanamespace`

`#kubectl delete rc namarc` secara default akan menghapus semua pod yang telah di created, maka `#kubectl delete rc namarc --cascade=false` seccara defaul `cascade=true`.

```
code fences
```
