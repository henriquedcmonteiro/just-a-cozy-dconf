# Cozy GNOME Terminal Theme

<b>My README was created with the help of ChatGPT to structure the content below.</b>

A custom GNOME Terminal profile with a cozy and minimal aesthetic.

This theme features:
- Dark background with a soft gradient
- Low-saturation green/yellow prompt for regular users
- Subtle red prompt when using root
- Clean, modern palette for directory listings
- Transparent background 

## Preview

<p align="left">
  <img src="/img/user-terminal.png" alt="Cozy theme - User mode" width="600"/>
</p>

<p align="left">
  <img src="/img/root-terminal.png" alt="Cozy theme - Root mode" width="600"/>
</p>

🛠️ How to Import This GNOME Terminal Profile
This repository contains a .dconf file to import a custom GNOME Terminal theme.

1. Install required package
Ensure you have dbus-x11 installed to allow dconf to work properly outside a desktop session:

```
sudo apt install dbus-x11
```
2. Start DBus session (only if needed)
If you get the error:

```
Failed to execute child process “dbus-launch” (No such file or directory)</b>
```
You can start a new DBus session manually:

```
eval "$(dbus-launch)"
```
3. Generate a UUID for your new profile
Run the command below to generate a unique identifier (UUID) for your GNOME Terminal profile:
```
uuidgen
```
Copy and use that UUID as the profile section header in your .dconf file like so:

```
[:df6baa20-27a3-49fd-a6b0-9ee54b79207c]
visible-name='Cozy'
...
```

4. Update your .dconf file structure
Make sure your .dconf file includes the list and default values like this:

```
[/]
list=['df6baa20-27a3-49fd-a6b0-9ee54b79207c']
default='df6baa20-27a3-49fd-a6b0-9ee54b79207c'

[:df6baa20-27a3-49fd-a6b0-9ee54b79207c]
visible-name='Cozy'
background-color='rgb(12,12,16)'
foreground-color='rgb(216,213,107)'
...
```
5. Load the profile
Finally, apply the configuration with:

```
dconf load /org/gnome/terminal/legacy/profiles:/ < your-file.dconf
```

