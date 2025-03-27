# Déploiement

Le déploiement se fait via ce script. Il est possible de personnaliser le fichier values.yaml auparavant ! 
```sh
./deploy.sh
```

Avant sa première utilisation, le vault doit être initialisé via le script init.  
5 clés et un token vont être générés. Il faudra les conserver en lieu sûr !
```sh
./init.sh
```

Il faut ensuite unseal le Vault
```sh
kubectl exec -it vault-0 -n karned -- vault operator unseal <clé1>
kubectl exec -it vault-0 -n karned -- vault operator unseal <clé2>
kubectl exec -it vault-0 -n karned -- vault operator unseal <clé3>
```

Le Vault est opérationnel.
```sh
kubectl exec -it vault-0 -n karned -- vault status
```

Connexion au Vault
```sh
kubectl exec -it vault-0 -n karned -- vault login <root_token>
```