# Install Oh-My-Posh on Windows

More info: <https://learn.microsoft.com/en-us/windows/terminal/tutorials/custom-prompt-setup>

More info on powershell profiles: <https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7.4>

### Step 1: Install Oh-My-Posh

```bash
winget install XP8K0HKJFRXGCK
```

Step 2: Add profile

Check if powershell profile file exists:

```bash
Test-Path -Path $PROFILE.AllUsersAllHosts
```

Usually wil return `false`

Run following to create profile:

```bash
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

Then open profile:

```bash
code $PROFILE
```

Paste following line into it:

```bash
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\paradox.omp.json" | Invoke-Expression
```

Replace `$env:POSH_THEMES_PATH\paradox.omp.json` to path of your own theme.

List of built-in Oh-My-Posh themes are at: https://ohmyposh.dev/docs/themes. Locate the .json filename and replace in profile config file.
