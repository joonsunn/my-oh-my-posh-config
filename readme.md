# My oh-my-posh setup

## Step 1 - Install Oh-My-Posh

Official instructions said to use

```bash
curl -s https://ohmyposh.dev/install.sh | bash -s
```

However that didn't work. So used the next suggested command:

```bash
curl -s https://ohmyposh.dev/install.sh | bash -s -- -d ~/bin
```

Also didn't work. Had to specify own directory as such:

```bash
curl -s https://ohmyposh.dev/install.sh | bash -s -- -d ~/.local/bin
```

## Step 2 - Install nerdfont

```bash
oh-my-posh font install
```

Picked 'DroidSansM Nerd Font'

## Step 3 - Added line to .bashrc

Added the following line

```bash
eval "$(oh-my-posh init bash"
```

## Step 4 - Changed theme

Modified Step 3 to be as follows:

```bash
eval "$(oh-my-posh init bash --config ~/.cache/oh-my-posh/themes/powerlevel10k_modern.omp.json)"
```

## Step 5 - Fix VS Code

Fonts not showing up correctly in VS Code. Need to change font to one of the NerdFonts for symbols to show up.

![Alt text](image.png)

## Step 6 - Modify config file to add code execution time

Make copy of any theme config to local folder with appropriate name

```bash
~/.config/oh-my-posh/themes/your-theme-config.json
```

Point oh-my-posh init in .bashrc to configure using own theme

```bash
eval "$(oh-my-posh init bash --config ~/.cache/oh-my-posh/themes/your-theme-config.json)"
```

Add following to right segment of config:

```json
{
 "type": "executiontime",
 "style": "powerline",
 "powerline_symbol": "",
 "foreground": "#ffffff",
 "background": "#8800dd",
 "template": " <#fefefe></> {{ .FormattedMs }} ",
 "properties": {
  "threshold": 500,
  "style": "austin",
  "always_enabled": true
 }
},
```
