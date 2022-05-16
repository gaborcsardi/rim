
# The R Installation Manager

Install, remove, configure R versions.

## 🚀  Features

  - Works on macOS, Windows and Linux (Ubuntu and Debian, x86\_64 and
    aarch64).
  - Easy installation and update, no system requirements on any
    platform.
  - Install multiple R versions.
  - Select the default R version, for the terminal and RStudio.
  - Select R version to install using symbolic names: `devel`, `next`,
    `release`, `oldrel`, etc.
  - Run multiple versions *at the same* time using quick links. E.g.
    `R-4.1` or `R-4.1.2` starts R 4.1.x. Quick links are automatically
    added to the user’s path.
  - On M1 macs select between x86\_64 and arm64 versions or R, or
    install both.
  - Creates and configures user level package libraries.
  - Restricts permissions to the system library. (On macOS, not needed
    on Windows and Linux).
  - Includes auto-complete for `zsh` and `bash`, on macOS and Linux.
  - Updates R installations to allow debugging with `lldb`, and to allow
    core dumps, on macOS.
  - Installs the appropriate Rtools versions on Windows and sets them
    up.
  - Cleans up stale R-related entries from the Windows registry.
  - Switches to root/administrator user as needed.

## 🐞  Known Issues

  - On macOS, `rig add` changes the default R version.
  - On macOS, R.app often does not work if you install multiple R
    versions.

Found another issue? Please report it in our [issue
tracker](https://github.com/gaborcsardi/rig/issues).

## ⬇️  Installation

### macOS (installer)

Download the latest release from
<https://github.com/gaborcsardi/rig/releases> and install it the usual
way.

### macOS (Homebrew)

If you use Homebrew (Intel or Arm version), you can install rig from our
tap:

``` sh
brew tap gaborcsardi/rig
brew install --cask rig
```

You can use x86\_64 rig on Arm macs, and it will be able to install Arm
builds of R. But you cannot use Arm rig on Intel macs. If you use both
brew versions, only install rig with one of them.

To update rig you can run

``` sh
brew upgrade --cask rig
```

### Windows (installer)

Download the latest release from
<https://github.com/gaborcsardi/rig/releases> and install it the usual
way.

`rig` adds itself to the user’s path, but you might need to restart your
terminal after the installation on Windows.

### Windows (Chocolatey)

If you use [Chocolatey](https://chocolatey.org/) (e.g. on GitHub
Actions) you can install `rig` with

``` powershell
choco install rig
```

and upgrade to the latest version with

``` powershell
choco upgrade rig
```

### Windows (Scoop)

If you use [Scoop](https://scoop.sh/), you can install rig from the
scoop bucket at
[`cderv/r-bucket`](https://github.com/cderv/r-bucket#r-installation-manager-rig):

``` powershell
scoop bucket add r-bucket https://github.com/cderv/r-bucket.git
scoop install rig
```

To update run

``` powershell
scoop update rig
```

### Linux

Download the latest releast from
<https://github.com/gaborcsardi/rig/releases> and uncompress it to
`/usr/local`

    curl -Ls https://github.com/gaborcsardi/rig/releases/download/v0.3.1/rig-linux-0.3.1.tar.gz |
      sudo tar xz -C /usr/local

If you are running Linux on arm64, download the arm64 build:

    curl -Ls https://github.com/gaborcsardi/rig/releases/download/v0.3.1/rig-linux-arm64-0.3.1.tar.gz |
      sudo tar xz -C /usr/local

Supported Linux distributions:

  - Ubuntu from
    [r-builds](https://github.com/rstudio/r-builds#r-builds), currently
    18.04, 20.04, 22.04.
  - Debian from
    [r-builds](https://github.com/rstudio/r-builds#r-builds), currently
    9, 10 and 11.

Other Linux distributions are coming soon.

### Auto-complete

The macOS and Linux installers also install completion files for `zsh`
and `bash`.

`zsh` completions work out of the box.

For `bash` completions install the `bash-completion` package from
Homebrew or your Linux distribution and make sure it is loaded from your
`.bashrc`. (You don’t need to install `bash` from Homebrew, but you can
if you like.)

## ⚙️  Usage

Use `rig add` to add a new R installation:

    rig add release

Use `rig list` to list the currently installed R versions, and `rig
default` to set the default one.

Run `rig` to see all commands and examples.

### Command list:

    rig add        -- install a new R version
    rig default    -- print or set default R version
    rig list       -- list installed R versions
    rig resolve    -- resolve a symbolic R version
    rig rm         -- remove R versions
    rig rstudio    -- start RStudio with the specified R version
    rig system     -- manage current installations

Run `rig <subcommand> --help` for information about a subcommand.

### macOS `rig system` subcommands

    rig system add-pak           -- install or update pak for an R version
    rig system allow-debugger    -- allow debugging R with lldb and gdb
    rig system allow-core-dumps  -- allow creating core dumps when R crashes
    rig system create-lib        -- create current user's package libraries
    rig system fix-permissions   -- restrict system library permissions to admin
    rig system forget            -- make system forget about R installations
    rig system make-links        -- create R-* quick links
    rig system make-orthogonal   -- make installed versions orthogonal
    rig system no-openmp         -- remove OpemMP (-fopenmp) option for Apple compilers

### Windows `rig system` subcommands

    rig system add-pak           -- install or update pak for an R version
    rig system clean-registry    -- clean stale R related entries in the registry
    rig system create-lib        -- create current user's package libraries
    rig system make-links        -- create R-* quick links

### Linux `rig system` subcommands

    rig system add-pak           -- install or update pak for an R version
    rig system create-lib        -- create current user's package libraries
    rig system make-links        -- create R-* quick links

## 🤝  Feedback

Please open an issue in our issue tracker at
<https://github.com/gaborcsardi/rig/issues>

## 📘  License

MIT 2021-2022 © RStudio Pbc.
