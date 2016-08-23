# AWS

> Connect to aws machine

> After download ec2 key ssh, go to the directory where key is download and use the following commands

```sh 
$ ssh -i ec2.pem ec2-user@54.86.15.222
```

> Creation de volume logique LVM

```sh
$ yum install lvm2    # installer le package permettant la création de volume 
```

> Notons que :

1. Toutes les commandes agissant sur les volumes physiques commencent par pv (pour physical volume)
2. Toutes les commandes agissant sur les groupes de volumes commencent par vg (pour volumes group)
3. Toutes les commandes agissant sur les volumes logiques commencent par lv (pour logical volume)

> Etape 1 : Créer un volume physique 

```sh
$ man -k ^pv    #  liste des commandes disponibles pour les volumes physiques
$ 
```
