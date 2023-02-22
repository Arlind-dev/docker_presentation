# Docker umgebung erstellen

### Docker installieren

Um Docker zu installieren und einfach benutzen zu können, müssen wir die folgenden Befehle ausführen:

```bash
sudo apt install apt-transport-https curl gnupg-agent ca-certificates software-properties-common -y
```

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

```bash
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

```bash
sudo usermod -aG docker $USER
```

```bash
newgrp docker
```
<br>

Diese Befehle installieren Docker auf einem Ubuntu-System und fügen den aktuellen Benutzer zur Gruppe "docker" hinzu, um Docker-Befehle ohne die Verwendung von "sudo" ausführen zu können.
