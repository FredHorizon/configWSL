# Tutorial de configuração Ubuntu 20.04 em WSL 2
[Clique aqui para seguir a playlist completa do tutorial no YouTube]()

## 1- Configuração inicial WSL2
[Seguir exatamente como esse tutorial](https://docs.microsoft.com/pt-br/windows/wsl/install-win10)

## 2- Instalação da build essentials e demais pacotes
```
sudo apt update && sudo apt upgrade
```
```
sudo apt install build-essential libssl-dev exuberant-ctags ncurses-term ack-grep silversearcher-ag fontconfig imagemagick libmagickwand-dev software-properties-common git vim-gtk3 curl
```
```
sudo apt install default-jdk
```
```
sudo apt install rar unrar
```
```
sudo apt update && sudo apt upgrade
```

## 3- Hyper terminal - Install/Config
* Site
  [site hyper](https://hyper.is/#installation)

* Fontes
  [Hack & MesloLGS](https://drive.google.com/file/d/1KkO0kuPT8L7ZIcBk5Dbm1LTvn4ft16MG/view?usp=sharing)
  [Fira_Code](https://drive.google.com/file/d/176PPAis-poktSth_L28n6XogbrrPazmw/view?usp=sharing)

* Preferências Hyper (CTRL+,)
  ```
  // Future versions of Hyper may add additional config options,
  // which will not automatically be merged into this file.
  // See https://hyper.is#cfg for all currently supported options.

  module.exports = {
    config: {
      // choose either `'stable'` for receiving highly polished,
      // or `'canary'` for less polished but more frequent updates
      updateChannel: 'stable',

      // default font size in pixels for all tabs
      fontSize: 12,

      // font family with optional fallbacks
      fontFamily: '"Fira Code", "MesloLGS NF"',

      // default font weight: 'normal' or 'bold'
      fontWeight: 'normal',

      // font weight for bold characters: 'normal' or 'bold'
      fontWeightBold: 'bold',

      // line height as a relative unit
      lineHeight: 1,

      // letter spacing as a relative unit
      letterSpacing: 0,

      // terminal cursor background color and opacity (hex, rgb, hsl, hsv, hwb or cmyk)
      cursorColor: 'rgba(196,196,196,0.8)',

      // terminal text color under BLOCK cursor
      cursorAccentColor: '#000',

      // `'BEAM'` for |, `'UNDERLINE'` for _, `'BLOCK'` for █
      cursorShape: 'BLOCK',

      // set to `true` (without backticks and without quotes) for blinking cursor
      cursorBlink: false,

      // color of the text
      foregroundColor: '#fff',

      // terminal background color
      // opacity is only supported on macOS
      backgroundColor: '#1A1A1A',

      // terminal selection color
      selectionColor: 'rgba(255,255,255,0.9)',

      // border color (window, tabs)
      borderColor: '#333',

      // custom CSS to embed in the main window
      css: '',

      // custom CSS to embed in the terminal window
      termCSS: '',

      // if you're using a Linux setup which show native menus, set to false
      // default: `true` on Linux, `true` on Windows, ignored on macOS
      showHamburgerMenu: '',

      // set to `false` (without backticks and without quotes) if you want to hide the minimize, maximize and close buttons
      // additionally, set to `'left'` if you want them on the left, like in Ubuntu
      // default: `true` (without backticks and without quotes) on Windows and Linux, ignored on macOS
      showWindowControls: '',

      // custom padding (CSS format, i.e.: `top right bottom left`)
      padding: '12px 14px',

      // the full list. if you're going to provide the full color palette,
      // including the 6 x 6 color cubes and the grayscale map, just provide
      // an array here instead of a color map object
      colors: {
        black: '#020B14',
        red: '#d32f2f',
        green: '#00c853',
        yellow: '#ffeb3b',
        blue: '#1565c0',
        magenta: '#C839C5',
        cyan: '#20C5C6',
        white: '#C7C7C7',
        lightBlack: '#686868',
        lightRed: '#FD6F6B',
        lightGreen: '#67F86F',
        lightYellow: '#FFFA72',
        lightBlue: '#6A76FB',
        lightMagenta: '#FD7CFC',
        lightCyan: '#68FDFE',
        lightWhite: '#FFFFFF',
      },

      // the shell to run when spawning a new session (i.e. /usr/local/bin/fish)
      // if left empty, your system's login shell will be used by default
      //
      // Windows
      // - Make sure to use a full path if the binary name doesn't work
      // - Remove `--login` in shellArgs
      //
      // Bash on Windows
      // - Example: `C:\\Windows\\System32\\bash.exe`
      //
      // PowerShell on Windows
      // - Example: `C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\powershell.exe`
      shell: '',

      // for setting shell arguments (i.e. for using interactive shellArgs: `['-i']`)
      // by default `['--login']` will be used
      shellArgs: ['--login'],

      // for environment variables
      env: {},

      // set to `false` for no bell
      bell: 'SOUND',

      // if `true` (without backticks and without quotes), selected text will automatically be copied to the clipboard
      copyOnSelect: false,

      // if `true` (without backticks and without quotes), hyper will be set as the default protocol client for SSH
      defaultSSHApp: true,

      // if `true` (without backticks and without quotes), on right click selected text will be copied or pasted if no
      // selection is present (`true` by default on Windows and disables the context menu feature)
      quickEdit: false,

      // choose either `'vertical'`, if you want the column mode when Option key is hold during selection (Default)
      // or `'force'`, if you want to force selection regardless of whether the terminal is in mouse events mode
      // (inside tmux or vim with mouse mode enabled for example).
      macOptionSelectionMode: 'vertical',

      // URL to custom bell
      // bellSoundURL: 'http://example.com/bell.mp3',

      // Whether to use the WebGL renderer. Set it to false to use canvas-based
      // rendering (slower, but supports transparent backgrounds)
      webGLRenderer: true,

      // for advanced config flags please refer to https://hyper.is/#cfg
      
      hyperCustomControls: {
        side: 'right', // Default: 'left'
        circleSize: 11, // Default: 11
        circleGap: 7.5, // Default: 7.5
        distanceToSide: 15, // Default: 15
        opacity: 1, // Default: 1
        hoverOpacity: 0.5, // Default: 0.5
  
        // Default controls below:
        // NOTE: You can remove a control, if you want to.
        controls: [
          {
            type: 'minimize',
            color: '#FBC536',
          },
          {
            type: 'maximize',
            color: '#39EA48',
          },
          {
            type: 'close',
            color: '#F24F55',
          },
        ],
      },
    },

    // a list of plugins to fetch and install from npm
    // format: [@org/]project[#version]
    // examples:
    //   `hyperpower`
    //   `@company/project`
    //   `project#1.0.1`
    plugins: ["hyper-custom-controls"],

    // in development, you can create a directory under
    // `~/.hyper_plugins/local/` and include it here
    // to load it and avoid it being `npm install`ed
    // localPlugins: ['hyper-omni'],

    keymaps: {
      // Example
      // 'window:devtools': 'cmd+alt+o',
    },
  };
  ```

## 4- ZSH & OH-MY-ZSH - Install/Config
```
sudo apt install zsh
```
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## 5- PowerLevel10k - Install/Config
* Clonar o tema
  ```
  git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
  ```

* adicionar o tema em `.zshrc`
  ```
  ZSH_THEME="powerlevel10k/powerlevel10k"
  ```

* Plugin Zinit
  ```
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"
  ```
  ```
  zinit light zdharma/fast-syntax-highlighting
  zinit light zsh-users/zsh-autosuggestions
  zinit light zsh-users/zsh-completions
  ```
* Plugin FZF
  ```
  git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf && ~/.fzf/install
  ```

## 6- ASDF - Install/Config
```
sudo apt install gnupg
```
```
sudo apt install bzip2
```
```
sudo apt install make
```
```
sudo apt-get install -y zlib1g-dev
```
```
sudo apt-get install -y sqlite3 libsqlite3-dev
```
```
sudo apt install -y libreadline-dev
```
```
sudo apt install wget
```
```
sudo apt-get install -y libssl-dev
```

* Clonar o repo e padronizar o terminal
```
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.0
```

```
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.zshrc
```
```
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.zshrc
```

```
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.zshrc
```
```
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.zshrc
```

### ASDF NODEJS
```
asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
```
```
bash -c '${ASDF_DATA_DIR:=$HOME/.asdf}/plugins/nodejs/bin/import-previous-release-team-keyring'
```

```Testes e final
asdf install nodejs latest ou 14.17.6
```
```
asdf global nodejs 14.17.6 ou 10.22.1
```
```
asdf list nodejs
```
```
node -v // verifica a versão atual que está sendo usada
```
```
asdf uninstall nodejs 14.17.6
```

```
asdf plugin-add yarn
```
```
asdf install yarn latest ou asdf install yarn 1.22.10
```
```
asdf global yarn 1.22.10
```
```
asdf list yarn
```

## 7- Git/GitHub - Config global user e chave SSH
```
git config --global user.name "nameuser"
```
```
git config --global user.email "emailuser@email.com"
```

```
git config --global user.name "FredHorizon"
```
```
git config --global user.email "fredoliveira.sys@gmail.com"
```

```
ssh-keygen -t rsa -C "emailuser@email.com"
```
```
cat /home/sgz/.ssh/id_rsa.pub
```
```
ssh -T git@github.com
```
