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
$ pvcreate /dev/xvdb        # Créer le volume physique 
```

> Etape 2 : Créer un volume groupe

```sh
$ vgcreate mvg /dev/xvdb      # Créer le volume groupe de nom mvg
```

> Etape 3 : Créer un volume logique 

```sh
$ lvcreate -n VolMapR -L 2g mvg      # Créer le VL
$ lvdisplay                          # Pour vérifier
```

> Etape 4 : Monter un système de fichier sur cette partition

```sh
$ mkfs -t ext4 /dev/mvg/VolMapR 
$ mount /dev/mvg/VolMapR /opt/mapr
$ df -h
```
