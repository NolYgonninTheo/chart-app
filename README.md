# Helm Charts Repository

Bienvenue dans mon dépôt de charts Helm. Ce dépôt contient divers charts pour faciliter le déploiement de vos applications sur Kubernetes.

## Ajouter ce dépôt

Pour ajouter ce dépôt à Helm, utilisez la commande suivante :

```sh
helm repo add my-helm-charts https://username.github.io/repo-name
```

Ensuite, mettez à jour votre dépôt Helm local pour récupérer les derniers charts :

```sh
helm repo update
```

## Charts Disponibles

### 1. chart-app

Ce chart déploie une application web. Notez que ce chart a une dépendance sur MySQL, qui est également déployée par ce chart.

**Installation :**

```sh
helm install my-app my-helm-charts/chart-app
```

**Valeurs configurables :**

| Clé                          | Description                                  | Valeur par défaut          |
| ---------------------------- | -------------------------------------------- | -------------------------- |
| `replicaCount`               | Nombre de réplicas pour l'application        | `1`                        |
| `mysql.image.repository`     | Référentiel de l'image Docker de MySQL       | `mysql`                    |
| `mysql.image.tag`            | Tag de l'image Docker de MySQL               | `8.0`                      |
| `mysql.auth.database`        | Nom de la base de données                    | `laravel`                  |
| `mysql.auth.username`        | Nom d'utilisateur de la base de données      | `mysqluser`                |
| `mysql.auth.password`        | Mot de passe de l'utilisateur                | `test12345`                |
| `mysql.auth.rootPassword`    | Mot de passe root                            | `root`                     |
| `mysql.primary.service.port` | Port du service MySQL                        | `3306`                     |
| `appli.name`                 | Nom de l'application                         | `application`              |
| `appli.image.repository`     | Référentiel de l'image Docker de l'application| `n22107670/sample-app`     |
| `appli.image.tag`            | Tag de l'image Docker de l'application       | `0.4.0`                    |
| `appli.service.type`         | Type de service Kubernetes                   | `ClusterIP`                |
| `appli.service.port`         | Port du service Kubernetes                   | `80`                       |
| `appli.ingress.enabled`      | Activer l'ingress pour l'application         | `true`                     |
| `appli.ingress.hosts`        | Hôte pour l'ingress                          | `kubequest.k3s.lifoto.co`  |
| `appli.ingress.tls`          | Configuration TLS pour l'ingress             | voir `values.yaml`         |

Pour plus d'informations, consultez le fichier `values.yaml`.

## Contribution

Si vous souhaitez contribuer à ce projet, veuillez soumettre une pull request ou ouvrir une issue. Toutes les contributions sont les bienvenues !

## Contact

Pour toute question, vous pouvez me contacter à [theoygo20@outlook.fr](mailto:theoygo20@outlook.fr).

Merci d'utiliser mes charts Helm !
