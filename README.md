# danisc

Mi tema para [Oh My Posh](https://ohmyposh.dev). Lo armé porque los que venían
traían demasiado: quería la ruta y la rama a la vista, y el resto solo cuando
hace falta.

Son dos líneas. Arriba va la carpeta, la rama de git y, si la carpeta es de un
proyecto Node, Python, Java o Flutter, la versión que corresponde. Abajo solo
una flecha, verde si el último comando salió bien y roja si falló. Cuando un
comando tarda más de un segundo aparece cuánto demoró, y si termina con error
se muestra el código.

La rama cambia de color: amarillo si está limpia, magenta si hay cambios sin
commitear y cian si está adelantada o atrasada respecto al remoto.

Usuario y host solo salen cuando estoy por SSH o como root.

Necesita una Nerd Font en la terminal para los iconos.

## Instalarlo en Windows

Primero Oh My Posh y la fuente. Yo uso Meslo:

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
oh-my-posh font install meslo
```

Cierra y vuelve a abrir la terminal para que tome el comando. Después, en la
configuración de Windows Terminal, pon `MesloLGM Nerd Font` como fuente del
perfil de PowerShell.

Luego baja el tema a `~\.poshthemes`:

```powershell
git clone https://github.com/HendaDev/danisc.git "$env:TEMP\danisc"
New-Item -ItemType Directory -Force "$env:USERPROFILE\.poshthemes" | Out-Null
Copy-Item "$env:TEMP\danisc\danisc.omp.json" "$env:USERPROFILE\.poshthemes\"
```

Y agrega esta línea al final del perfil (`notepad $PROFILE`; si no existe,
créalo con `New-Item -Force $PROFILE`):

```powershell
oh-my-posh init pwsh --config "$env:USERPROFILE\.poshthemes\danisc.omp.json" | Invoke-Expression
```

Abre otra terminal y ya debería verse.

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
cp /tmp/danisc/danisc.omp.json ~/.poshthemes/
```

Y al final del `~/.bashrc`:

```bash
eval "$(oh-my-posh init bash --config ~/.poshthemes/danisc.omp.json)"
```

Para verlo sin cerrar la terminal: `exec bash`.

Si ya tenías otro prompt configurado en el `.bashrc` (oh-my-bash, un `PS1`
propio), coméntalo, porque si no se pisan.

## Si algo se ve raro

Si en lugar de iconos ves cuadritos o signos de pregunta, la terminal no está
usando la Nerd Font. En Windows también ayuda tener esto en el perfil, antes de
la línea de Oh My Posh:

```powershell
[Console]::OutputEncoding = [System.Text.Encoding]::UTF8
```
