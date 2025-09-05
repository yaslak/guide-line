# Le style, c'est l'Homme

Quand mon PC entre en veille, il devient une toile vivante. Des vidéos en boucle défilent comme des instantanés de ma journée et des reflets de mon style. Chaque animation capture un fragment de ma personnalité et transforme l’écran en un espace où mon identité se déploie librement.



# Process Manager Script
Script Unix pour démarrer et arrêter facilement des processus en arrière-plan.

## 1. Installation
Créez le fichier :
```bash
sudo nano /usr/local/bin/process
```

## 2. Copiez-collez ce code :
```bash
#!/bin/bash
DEFAULT_PROCESS="caffeinate"
ACTION="$1"
PROCESS_NAME="${2:-$DEFAULT_PROCESS}"

start_process() {
    nohup "$@" > /dev/null 2>&1 &
    echo "Processus démarré (PID: $!)"
}

kill_process() {
    PIDS=$(pgrep -x "$PROCESS_NAME")
    [ -z "$PIDS" ] && echo "Aucun processus '$PROCESS_NAME' en cours." && return
    for PID in $PIDS; do kill -9 "$PID" 2>/dev/null; done
    echo "Processus '$PROCESS_NAME' terminés."
}

case "$ACTION" in
    start)
        shift
        if [ $# -eq 0 ]; then
            start_process caffeinate -dimsu  # ← MODIFIÉ ICI
        else
            start_process "$@"
        fi
        ;;
    kill|stop)
        kill_process
        ;;
    *)
        echo "Usage: process [start|kill] [nom_processus]"
        exit 1
        ;;
esac
```

## 3. Rendez-le exécutable :
```bash
sudo chmod +x /usr/local/bin/process
```
---
## 4. Utilisation
Démarrer caffeinate (par défaut) :
```bash
process start
```

## 5. Arrêter caffeinate :
```bash
process kill
```

## 6. Démarrer un autre processus :
```bash
process start sleep 3600
```

## 7. Arrêter un processus spécifique (ex: Zoom):
```bash
process kill zoom
```

## 8. Enchaînement de Commandes :
Le script accepte n'importe quelle commande après start. Utilisez la syntaxe normale shell pour passer des arguments :
```bash
process start [votre_commande] [vos_arguments]
```
### Exemples :
```bash
process start sleep 3600        # Dort pendant 1 heure
process start top               # Lance le moniteur système
process start ping google.com   # Lance un ping continu
```

#### NB: Le script executera exactement la commande fournie après `start` en arrière-plan avec `nohup.
