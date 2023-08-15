La commande **git config** permet de changer les variables de configuration

### configurer son identité

Pour configurer son adresse mail et son nom : 

```bash
git config --global user.name "Micka"
git config --global user.mail "micka@gmail.com"
```

### Configurer son éditeur de text

```bash
git config --global core.editor vscode
```

### Vérifier vos paramètres

```bash
git config --list
```
