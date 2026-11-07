# danisc

Tema sencillo y agradable

Sencillo para visualizar en que rama del proyecto te encuentras, tonos de colores agradables y 
visualización rápida de lenguaje con el que estas trabajando.

Los colores son hex fijos en tonos medios, así se ven igual en temas claros y
oscuros de la terminal.

Necesitas una Nerd Font en la terminal para los iconos.

## Instalarlo en Windows

FUente que uso: Meslo

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
oh-my-posh font install meslo
```

## Instalarlo en Linux

Con bash. Oh My Posh se instala en `~/.local/bin`:

```bash
curl -s https://ohmyposh.dev/install.sh | bash -s
oh-my-posh font install meslo
```

En las preferencias de la terminal elige `MesloLGM Nerd Font`.

El tema:

```bash
git clone https://github.com/HendaDev/danisc.git /tmp/danisc
mkdir -p ~/.poshthemes
```

Y al final del `~/.bashrc`:

```bash
eval "$(oh-my-posh init bash --config ~/.poshthemes/danisc.omp.json)"
```

Para verlo sin cerrar la terminal: `exec bash`.

Si ya tenías otro prompt configurado en el `.bashrc` (oh-my-bash, un `PS1`
propio), coméntalo, porque si no se pisan.
