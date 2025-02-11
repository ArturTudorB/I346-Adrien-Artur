# Laboratoire S3

## Installation et configuration du CLI

* [Installer le client git](https://git-scm.com/)
  * Git bash vous embarque de nombreuses commandes Linux utiles pour s'entrainer avec S3 (cat, grep, touch, ls)
* [Installation du CLI - v2](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
* [Configuration du CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-quickstart.html#getting-started-quickstart-existing)
  * Les clés vous ont été partagées par oneDrive
* [Gestion des profiles](https://docs.aws.amazon.com/cli/v1/userguide/cli-configure-files.html#cli-configure-files-format-profile)
  * Vous devez créer un profile du nom de votre équipe et l'utiliser pour toute les futures commandes
  ```
  aws s3 <la commande> --profile devopsteam<xx>
  ```

## IAM Policy

Voici la "policy" qui vous a été attribuée:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "s3:ListAllMyBuckets",
            "Resource": "arn:aws:s3:::*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:GetObject",
                "s3:DeleteObject",
            ],
            "Resource": "arn:aws:s3:::devopsteam<XX>-i346/*" //XX -> devopsteam number
        }
    ]
}
```

## Exploiter un S3

Attention:
* Vous devez utiliser la v2 du CLI
* Le client offre soit la commande s3, soit s3api. En priorité vous devez essayer "s3".

### Créer un bucket

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* Le bucket existe-t-il ?

```bash
aws s3 ls --profile devopsteam07 | grep "devopsteam*"
```

```
[OUTPUT]
2025-01-27 22:23:30 devopsteam01-i346
2025-01-27 22:28:03 devopsteam02-i346
2025-01-27 22:28:05 devopsteam03-i346
2025-01-27 22:28:06 devopsteam04-i346
2025-01-27 22:28:08 devopsteam05-i346
2025-01-27 22:28:09 devopsteam06-i346
2025-01-27 22:28:11 devopsteam07-i346
2025-01-27 22:28:13 devopsteam08-i346
2025-01-27 22:28:14 devopsteam09-i346
2025-01-27 22:28:16 devopsteam10-i346
2025-02-03 19:32:33 devopsteam99-i346
```

* Créer un bucket (via un compte admin)

```bash
aws s3 mb s3://devopsteam99-i346 --region eu-central-1 --profile s3-admin
```

```
[OUTPUT]
make_bucket: devopsteam99-i346
```


### Uploader un fichier

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
On ne peut pas vérifier l'état du bucket avant la commande'
```

```
[OUTPUT]
//TODO
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
aws s3 cp C:/Dev/C295/premier-projet/src/main.js s3://devopsteam07-i346 --profil devopsteam07

```

```
[OUTPUT]
upload: C:\Dev\C295\premier-projet\src\main.js to s3://devopsteam07-i346/main.js
```

### Uploader un répertoire

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 cp C:/Dev/C295/premier-projet/src s3://devopsteam07-i346 --profil devopsteam07 --recursive


```

```
[OUTPUT]
upload: C:\Dev\C295\premier-projet\src\app.module.js to s3://devopsteam07-i346/app.module.js
upload: C:\Dev\C295\premier-projet\src\app.controller.js to s3://devopsteam07-i346/app.controller.js
upload: C:\Dev\C295\premier-projet\src\app.controller.spec.js to s3://devopsteam07-i346/app.controller.spec.js
upload: C:\Dev\C295\premier-projet\src\app.service.js to s3://devopsteam07-i346/app.service.js
upload: C:\Dev\C295\premier-projet\src\main.js to s3://devopsteam07-i346/main.js

```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
//TODO
aws s3 ls s3://devopsteam07-i346/srx --profil devopsteam07
```

```
[OUTPUT]
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam07-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam07-i346" because no identity-based policy allows the s3:ListBucket action

```

### Lister le contenu d'un "repertoire"

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
//TODO
```

```
[OUTPUT]
//TODO
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
aws s3 ls s3://devopsteam07-i346 --profile devopsteam07
```

```
[OUTPUT]
[OUTPUT]An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam07-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam07-i346" because no identity-based policy allows the s3:ListBucket action
```

### Synchroniser un répertoire local de sa machine avec un bucket

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
//TODO
```

```
[OUTPUT]
//TODO
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
aws s3 sync C:/testeUpload s3://devopsteam07-i346 --profile devopsteam07
```

```
[OUTPUT]
//fatal error: An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam07-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam07-i346" because no identity-based policy allows the s3:ListBucket action
```

### Publier un fichier présent sur un bucket en générant un lien (url) temporaire

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
//TODO
```

```
[OUTPUT]
//TODO
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
//aws s3 presign s3://devopsteam07-i346/test1.txt --expires-in 3600 --region eu-central-1 --profile devopsteam07
```

```
[OUTPUT]
//[OUTPUT]https://devopsteam07-i346.s3.eu-central-1.amazonaws.com/test1.txt?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA2KFJKL4OZNTJHHVP%2F20250211%2Feu-central-1%2Fs3%2Faws4_request&X-Amz-Date=20250211T132648Z&X-Amz-Expires=3600&X-Amz-SignedHeaders=host&X-Amz-Signature=b63675db97a43a2a3d9cc1728c9cd08cc323b7e7bc75dd5fa8d047500479773b
```

### Supprimer un fichier

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash


```

```
[OUTPUT]


```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
//aws s3 rb s3://devopsteam07 --profil devopsteam07
```

```
[OUTPUT]
//remove_bucket: mybucket
```

### Vider un "repertoire"

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
//TODO
```

```
[OUTPUT]
//TODO
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
aws s3 rm s3://devopsteam07 --profil devopsteam07 --recursive
```

```
[OUTPUT]
delete: s3://devopsteam07/test1.txt
delete: s3://devopsteam07/test2.txt
```

### Extraire uniquement les metadonnées d'un objet

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
//TODO
```

```
[OUTPUT]
//TODO
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash

```

```
[OUTPUT]

```

### Vider le bucket

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
//TODO
```

```
[OUTPUT]
//TODO
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
//TODO
```

```
[OUTPUT]
//TODO
```

---

## Questions d'analyse

Consigne : répondre en utilisant des sources officielles et en vous appuyant dessus pour répondre.

### Pourquoi est-il déconseillé de détruire un bucket S3 selon AWS ?

* https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/rb.html#description

//Parce que c'est irréversible et que les données seront perdues

### Quelle est la différence entre un Bucket S3 et Glacier ?

* https://awscli.amazonaws.com/v2/documentation/api/latest/reference/glacier/index.html?highlight=glacier

Le glacier, c'est pour stocker des données à long terme avec une solution de stockage spécifique pour le "cold data", alors que le bucket S3 c'est pour stocker des données à court terme

### Reprenez l'IAM "Policy" et expliquer ce que vous pouvez en déduire au niveau des droits qui vous sont alloués

Consigne : Reprenez la "policy" et documenter chaque ligne


{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow", //Autorisation pour les actions suivantes
      "Action": "s3:ListAllMyBuckets", //Lister les buckets
      "Resource": "arn:aws:s3:::*" //Dans tous les buckets
    },
    {
      "Effect": "Allow", //Autorisation pour les actions suivantes
      "Action": [
      "s3:PutObject", //Rajouter un objet
      "s3:GetObject", //Récupérer un objet
      "s3:DeleteObject", //Supprimer un objet
      ],
        "Resource": "arn:aws:s3:::devopsteam<XX>-i346/*" //XX -> devopsteam number 
      }
    ]
}