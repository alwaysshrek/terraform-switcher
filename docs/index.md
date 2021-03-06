# Terraform Switcher 

The `tfswitch` command line tool lets you switch between different versions of [terraform](https://www.terraform.io/){:target="_blank"}. 
If you do not have a particular version of terraform installed, `tfswitch` will download the version you desire.
The installation is minimal and easy. 
Once installed, simply select the version you require from the dropdown and start using terraform. 

<hr>

## Installation

`tfswitch` is available for MacOS and Linux based operating systems.

### Homebrew

Installation for MacOS is the easiest with Homebrew. [If you do not have homebrew installed, click here](https://brew.sh/){:target="_blank"}. 


```ruby
brew install warrensbox/tap/tfswitch
```

### Linux

Installation for Linux operation systems.

```sh
curl -L https://raw.githubusercontent.com/warrensbox/terraform-switcher/release/install.sh | bash
```

### Install from source

Alternatively, you can install the binary from the source [here](https://github.com/warrensbox/terraform-switcher/releases) 

<hr>

## How to use:
### Use dropdown menu to select version
<img align="center" src="https://s3.us-east-2.amazonaws.com/kepler-images/warrensbox/tfswitch/tfswitch.gif" alt="drawing" style="width: 480px;"/>

1.  You can switch between different versions of terraform by typing the command `tfswitch` on your terminal. 
2.  Select the version of terraform you require by using the up and down arrow.
3.  Hit **Enter** to select the desired version.

The most recently selected versions are presented at the top of the dropdown.

### Supply version on command line
<img align="center" src="https://s3.us-east-2.amazonaws.com/kepler-images/warrensbox/tfswitch/tfswitch-v4.gif" alt="drawing" style="width: 480px;"/>

1. You can also supply the desired version as an argument on the command line.
2. For example, `tfswitch 0.10.5` for version 0.10.5 of terraform.
3. Hit **Enter** to switch.

### See all versions including beta, alpha and release candidates(rc)
<img src="https://s3.us-east-2.amazonaws.com/kepler-images/warrensbox/tfswitch/tfswitch-v5.gif" alt="drawing" style="width: 490px;"/>

1. Display all versions including beta, alpha and release candidates(rc). 
2. For example, `tfswitch -l` or `tfswitch --list-all` to see all versions.
3. Hit **Enter** to select the desired version.


### Use .tfswitchrc file
<img src="https://s3.us-east-2.amazonaws.com/kepler-images/warrensbox/tfswitch/tfswitch-v6.gif" alt="drawing" style="width: 490px;"/>

1. Create a `.tfswitchrc` file containing the desired version.
2. For example, `echo "0.10.5" >> .tfswitchrc` for version 0.10.5 of terraform.
3. Run the command `tfswitch` in the same directory as your `.tfswitchrc`.


**Automatically switch with bash**

Add the following to the end of your `~/.bashrc` file:
```
cdtfswitch(){
  builtin cd "$@";
  cdir=$PWD;
  if [ -f "$cdir/.tfswitchrc" ]; then
    tfswitch
  fi
}
alias cd='cdtfswitch'
```

**Automatically switch with zsh**

Add the following to the end of your `~/.zshrc` file:

```
load-tfswitch() {
  local tfswitchrc_path=".tfswitchrc"

  if [ -f "$tfswitchrc_path" ]; then
    tfswitch
  fi
}
add-zsh-hook chpwd load-tfswitch
load-tfswitch
```

*older version of zsh*
```
cd(){
  builtin cd "$@";
  cdir=$PWD;
  if [ -f "$cdir/.tfswitchrc" ]; then
    tfswitch
  fi
}
```

<hr>

## Issues

Please open  *issues* here: [New Issue](https://github.com/warrensbox/terraform-switcher/issues){:target="_blank"}

<hr>

See how to *upgrade*, *uninstall*, *troubleshoot* here:
[Additional Info](additional)