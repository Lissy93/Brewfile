
<h1 align="center">Lissy93/Brewfile</h1>
<p align="center"><i>My list of *nix packages to be installed on MacOS via Homebrew, for the ultimate dev setup</i></p>
<p align="center">
  <a href="https://github.com/lissy93/brewfile/">
    <img width="120" src="https://i.ibb.co/LhhDNg7/brewfile-repo-logo.png" />
  </a>
</p>


## Getting Started



To get started, install [Homebrew](https://docs.brew.sh/Installation), then just download the [`Brewfile`](https://github.com/Lissy93/Brewfile/blob/master/Brewfile) to `~/.Brewfile`, make any desired changes, and run `brew bundle --global` to install the listed packages. Done 🍻

---

Alternatively, there's a guided install process, which can be initiated with:

```bash
bash <(curl -s https://lissy93.github.io/Brewfile/install.sh)
```

<p align="center">
  <a href="https://lissy93.github.io/Brewfile" title="Screenshot of the guided installation script">
    <img width="650" src="https://i.ibb.co/g63WYBF/brewfile-install-script.png" alt="Brewfile automated installation script" />
  </a>
</p>

>  [!NOTE]
> To keep track of your own personal package list [fork](https://github.com/Lissy93/Brewfile/fork) this repo<br>
> And don't forget to replace [lissy93] with your own username!

---

## About Homebrew

[Homebrew](https://brew.sh/) is an unofficial package manager for MacOS, that makes installing, updating and managing user applications easier.

It only ever installs packages within it's prefix, but then symlinks them to the appropriate place on disk. And since it's just Git and Ruby underneath, it's easy to modify to your liking, and roll back changes if necissary.

Homebrew is used via the terminal, with the `brew` command, but there is an unofficial GUI, [Cakebrew](https://github.com/brunophilipe/Cakebrew). For more infomation, take a look at the [Documentation](https://docs.brew.sh/).

---

## Understanding the Brewfile

The Brewfile defines a list of packages, that you'd like to install on your system.

It includes several keywords, like `brew`, `cask`, `tap`, `mas`, etc - this is explained in detail in the [terminology](https://docs.brew.sh/Manpage#terminology) section of the docs. But in short: Lines which start with brew are packages that are installed via their pre-compiled binaries. Where as casks are applications that require an installer (typically GUI apps). Taps just add additional repositories, and are used when an app's formula isn't published to the main Homebrew repo. And mas is a plugin that enables you to install apps from the Apple App Store from within your Brewfile.

---

## Package List

The following packages will be installed, with the aim to setup a fully-featured development machine.

<details>
<summary><b>Click to expand full package list</b> ↕️</summary>

> **Note**: _Be sure to remove anything that you do not need before installing._

### Command Line

<details>
<summary>CLI Essentials</summary>

- [`git`](https://git-scm.com/) - Version controll
- [`neovim`](https://neovim.io/) - Text editor
- [`ranger`](https://ranger.github.io/) - Directory browser
- [`tmux`](https://github.com/tmux/tmux/wiki) - Term multiplexer

</details>

<details>
<summary>CLI Basics</summary>

- [`aria2`](https://github.com/aria2/aria2) - Resuming download util _(better wget)_
- [`bat`](https://github.com/sharkdp/bat) - Output highlighting _(better cat)_
- [`ctags`](https://github.com/universal-ctags/ctags) - Indexing of file info + headers
- [`diff-so-fancy`](https://github.com/so-fancy/diff-so-fancy) - Readable file compares _(better diff)_
- [`entr`](https://eradman.com/entrproject/) - Run command whenever file changes
- [`duf`](https://github.com/muesli/duf) - Get info on mounted disks _(better df)_
- [`exa`](https://github.com/ogham/exa) - Listing files with info _(better ls)_
- [`exiftool`](https://exiftool.org/) - Reading and writing exif metadata
- [`fdupes`](https://github.com/jbruchon/jdupes) - Duplicate file finder
- [`fzf`](https://github.com/junegunn/fzf) - Fuzzy file finder and filtering
- [`hyperfine`](https://github.com/sharkdp/hyperfine) - Benchmarking for arbitrary commands
- [`jq`](https://github.com/stedolan/jq) - JSON parser
- [`most`](https://www.jedsoft.org/most/) - Multi-window scroll pager _(better less)_
- [`procs`](https://github.com/dalance/procs) - Advanced process viewer _(better ps)_
- [`ripgrep`](https://github.com/BurntSushi/ripgrep) - Searching within files _(better grep)_
- [`rsync`](https://rsync.samba.org/) - Fast, incremental file transfer
- [`scc`](https://github.com/boyter/scc) - Count lines of code _(better cloc)_
- [`sd`](https://github.com/chmln/sd) - RegEx find and replace _(better sed)_
- [`thefuck`](https://github.com/nvbn/thefuck) - Auto-correct miss-typed commands
- [`tldr`](https://github.com/tldr-pages/tldr) - Community-maintained docs _(better man)_
- [`tree`](https://gitlab.com/OldManProgrammer/unix-tree) - Directory listings as tree
- [`trash-cli`](https://github.com/andreafrancia/trash-cli) - Record + restore removed files
- [`watch`](https://gitlab.com/procps-ng/procps) - Run commands periorically
- [`xsel`](https://github.com/kfish/xsel) - Copy paste access to X clipboard
- [`zoxide`](https://github.com/ajeetdsouza/zoxide) - Easy navigation _(better cd)_

</details>

<details>
<summary>CLI Monitoring and Performance Apps</summary>

- [`bandwhich`](https://github.com/imsnif/bandwhich) - Bandwidth utilization monitor 
- [`ctop`](https://github.com/bcicen/ctop) - Container metrics and monitoring
- [`bpytop`](https://github.com/aristocratos/bpytop) - Resource monitoring _(like htop)_
- [`glances`](https://github.com/nicolargo/glances) - Resource monitor + web and API
- [`gping`](https://github.com/orf/gping) - Interactive ping tool, with graph
- [`ncdu`](https://dev.yorhel.nl/ncdu) - Disk usage analyzer and monitor _(better du)_
- [`speedtest-cli`](https://github.com/sivel/speedtest-cli) - Command line speed test utility

</details>

<details>
<summary>CLI Productivity Apps</summary>

- [`browsh`](https://github.com/browsh-org/browsh) - CLI web browser
- [`buku`](https://github.com/jarun/buku) - Bookmark manager
- [`cmus`](https://github.com/cmus/cmus) - Music browser / player
- [`khal`](https://github.com/pimutils/khal) - Calendar client
- [`mutt`](https://gitlab.com/muttmua/mutt) - Email client
- [`newsboat`](https://github.com/newsboat/newsboat) - RSS / ATOM news reader
- [`rclone`](https://github.com/rclone/rclone) - Manage cloud storage
- [`task`](https://github.com/GothenburgBitFactory/taskwarrior) - Todo + task management

</details>

<details>
<summary>CLI Dev Suits</summary>

- [`httpie`](https://httpie.io/) - HTTP / API testing testing client
- [`lazydocker`](https://github.com/jesseduffield/lazydocker) - Full Docker management app
- [`lazygit`](https://github.com/jesseduffield/lazygit) - Full Git managemtne app

</details>

<details>
<summary>CLI External Sercvices</summary>

- [`ngrok`](https://ngrok.com/) - Reverse proxy for sharing localhost
- [`tmate`](https://github.com/tmate-io/tmate) - Share a terminal session via internet
- [`asciinema`](https://asciinema.org/) - Recording + sharing terminal sessions
- [`navi`](https://github.com/denisidoro/navi) - Browse, search, read cheat sheets

</details>

<details>
<summary>CLI Fun</summary>

- [`cowsay`](https://github.com/piuccio/cowsay) - Have an ASCII cow say your message
- [`figlet`](http://www.figlet.org/) - Output text as big ASCII art text
- [`lolcat`](https://github.com/busyloop/lolcat) - Make console output raibow colored
- [`neofetch`](https://github.com/dylanaraps/neofetch) - Show system data and ditstro info

</details>

### Software Development

<details>
<summary>Development Apps</summary>

- [Android Studio](https://developer.android.com/studio/) - IDE for Android development
- [Boop](https://github.com/IvanMathy/Boop) - Test transformation tool _(MacOS Only)_
- [iterm2](https://iterm2.com/) - Better terminal emulator _(MacOS Only)_
- [Postman](https://www.postman.com/) - HTTP API testing app
- [Sourcetree](https://www.sourcetreeapp.com/) - Git visual client _(MacOS Only)_
- [Virtual Box](https://www.virtualbox.org/) - VM management console
- [VS Code](https://code.visualstudio.com/) - Code editor

</details>

<details>
<summary>Development Langs, Compilers, Package Managers and SDKs</summary>

- `docker` - Containers
- `gcc` - GNU C++ compilers
- `go` - Compiler for Go Lang
- `gradle` - Build tool for Java
- `lua` - Lua interpreter
- `luarocks` - Package manager for Lua
- `node` - Node.js
- `nvm` - Switching node versions
- `openjdk` - Java development kit
- `python` - Python interpriter
- `rust` - Rust language
- `android-sdk` - Android software dev kit

</details>

<details>
<summary>Development Utils</summary>

- [`gh`](https://cli.github.com/) - Interact with GitHub PRs, issues, repos
- [`scrcpy`](https://github.com/Genymobile/scrcpy) - Display and control Andrdroid devices
- [`terminal-notifier`](https://github.com/julienXX/terminal-notifier) - Trigger Mac notifications from terminal _(MacOS Only)_
- [`tig`](https://jonas.github.io/tig/) - Text-mode interface for git
- [`ttygif`](https://github.com/icholy/ttygif) - Generate GIF from terminal commands + output

</details>

<details>
<summary>Network and Security Testing</summary>

- [`bettercap`](https://www.bettercap.org/) - Network, scanning and moniroting
- [`nmap`](https://nmap.org/) - Port scanning
- [`wrk`](https://github.com/giltene/wrk2) - HTTP benchmarking
- [`burp-suite`](https://portswigger.net/burp) - Web security testing
- [`metasploit`](https://www.metasploit.com/) - Pen testing framework
- [`owasp-zap`](https://owasp.org/www-project-zap/) - Web app security scanner
- [`wireshark`](https://www.wireshark.org/) - Network analyzer + packet capture

</details>

<details>
<summary>Security Utilities</summary>

- [`bcrypt`](https://bcrypt.sourceforge.net/) - Encryption utility, using blowfish
- [`clamav`](https://www.clamav.net/) - Open source virus scanning suite
- [`git-crypt`](https://www.agwa.name/projects/git-crypt/) - Transparent encryption for git repos
- [`lynis`](https://cisofy.com/lynis/) - Scan system for common security issues
- [`openssl`](https://www.openssl.org/) - Cryptography and SSL/TLS Toolkit
- [`rkhunter`](https://rkhunter.sourceforge.net/) - Search / detect potential root kits
- [`veracrypt`](https://www.veracrypt.fr/code/VeraCrypt/) - File and volume encryption

</details>

### Desktop Applications

<details>
<summary>Creativity</summary>

- [Audacity](https://www.audacityteam.org/) - Multi-track audio editor and recording
- [Blender](https://www.blender.org/) - 3D modelling, rendering and sculpting
- [Cura](https://ultimaker.com/software/ultimaker-cura) - 3D Printing software, for slicing models
- [DarkTable](https://www.darktable.org/) - Organize and bulk edit photos (similar to Lightroom)
- [Dia](https://wiki.gnome.org/Apps/Dia) - Versatile diagramming tool, useful for UML
- [Gimp](https://www.gimp.org/) - Image and photo editing application
- [HandBrake](https://handbrake.fr/) - For converting video from any format to a selection of modern codecs
- [InkScape](https://inkscape.org/) - Digital drawing/ illustration
- [OBS Studio](https://obsproject.com/) - Streaming and screencasting
- [Shotcut](https://www.shotcut.org/) - Video editor
- [Synfig Studio](https://www.synfig.org/) - 2D animation

</details>

<details>
<summary>Media</summary>

- [Calibre](https://calibre-ebook.com/) - E-Book reader
- [Spotify](https://spotify.com) - Propietary music streaming
- [Transmission](https://transmissionbt.com/) - Torrent client
- [VLC](https://www.videolan.org/vlc/) - Media player
- [Pandoc](https://pandoc.org/) - Universal file converter
- [Youtube-dl](https://youtube-dl.org/) - YouTube video downloader

</details>

<details>
<summary>Personal Applications</summary>

- [1Password](https://1password.com/) - Password manager _(proprietary)_
- [Tresorit](https://tresorit.com/) - Encrypted file backup _(proprietary)_
- [Standard Notes](https://standardnotes.com/) - Encrypted synced notes
- [Signal](https://www.signal.org) - Link to encrypted mobile messenger
- [Ledger Live](https://www.ledger.com/ledger-live) - Crypto hardware wallet manager
- [ProtonMail-Bridge](https://proton.me/mail/bridge) - Decrypt ProtonMail emails
- [ProtonVPN](https://protonvpn.com/) - Client app for ProtonVPN

</details>

<details>
<summary>Browsers</summary>

- [Firefox](https://www.mozilla.org/en-GB/firefox/)
- [Chromium](https://github.com/ungoogled-software/ungoogled-chromium)
- [Tor](https://www.torproject.org/)

</details>

### MacOS Apps

<details>
<summary>MacOS Mods and Imrovments</summary>

- `alt-tab` - Much better alt-tab window switcher
- `anybar` - Custom programatic menubar icons
- `copyq` - Clipboard manager _(cross platform)_
- `espanso` - Live text expander _(cross-platform)_
- `finicky` - Website-specific default browser
- `hiddenbar` - Hide / show annoying menubar icons
- `iproute2mac` - MacOS port of netstat and ifconfig
- `lporg` - Backup and restore launchpad layout
- `m-cli` - All in one MacOS management CLI app
- `mjolnir` - Util for loading Lua automations
- `openinterminal` - Finder button, opens directory in terminal
- `popclip` - Popup options for text on highlight
- `raycast` - Spotlight alternative
- `shottr` - Better screenshot utility
- `skhd` - Hotkey daemon for macOS
- `stats` - System resource usage in menubar
- `yabai` - Tiling window manager

</details>

</details>

---

## Bigger Picture

The Brewfile is really useful to incorporate into your dotfiles, or for quickly setting up new machines.
You can see how I am using this in [Lissy93/Dotfiles](https://github.com/Lissy93/dotfiles).
Other package managers have similar features. For example, [here's the scripts](https://github.com/Lissy93/dotfiles/tree/master/scripts/installs) I use to manage my package list for Arch, Debian, Alpine and MacOS.

---

## Contributing

Contributions are welcome :)
If you're new to GitHub, see the [documentation](https://docs.github.com/en/get-started/quickstart/contributing-to-projects) for a step-by-step guide on how to submit edits to projects.

Changes to the Brewfile should be made up-stream, directly into [Lissy93/Dotfiles](https://github.com/lissy93/dotfiles) (in [`Brewfile`](https://github.com/Lissy93/dotfiles/blob/master/scripts/installs/Brewfile)), which will then be automatically synced to this repo.

---

## License

> [!NOTE]
> > For licenses for each package listed here, see their websites _(linked to [above](#package-list))_.

> _**[Lissy93/Brewfile](https://github.com/Lissy93/Brewfile)** is licensed under [MIT](https://github.com/Lissy93/Brewfile/blob/HEAD/LICENSE) © [Alicia Sykes](https://aliciasykes.com) 2022._<br>
> <sup align="right">For information, see <a href="https://tldrlegal.com/license/mit-license">TLDR Legal > MIT</a></sup>

<details>
<summary>Expand License</summary>

```
The MIT License (MIT)
Copyright (c) Alicia Sykes <alicia@omg.com> 

Permission is hereby granted, free of charge, to any person obtaining a copy 
of this software and associated documentation files (the "Software"), to deal 
in the Software without restriction, including without limitation the rights 
to use, copy, modify, merge, publish, distribute, sub-license, and/or sell 
copies of the Software, and to permit persons to whom the Software is furnished 
to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included install 
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANT ABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NON INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

</details>

---

<!-- License + Copyright -->
<p  align="center">
  <i>© <a href="https://aliciasykes.com">Alicia Sykes</a> 2022-23</i><br>
  <i>Licensed under <a href="https://gist.github.com/Lissy93/143d2ee01ccc5c052a17">MIT</a></i><br>
  <a href="https://github.com/lissy93"><img src="https://i.ibb.co/4KtpYxb/octocat-clean-mini.png" /></a><br>
  <sup>Thanks for visiting :)</sup>
</p>

<!-- Dinosaur -->
<!-- 
                        . - ~ ~ ~ - .
      ..     _      .-~               ~-.
     //|     \ `..~                      `.
    || |      }  }              /       \  \
(\   \\ \~^..'                 |         }  \
 \`.-~  o      /       }       |        /    \
 (__          |       /        |       /      `.
  `- - ~ ~ -._|      /_ - ~ ~ ^|      /- _      `.
              |     /          |     /     ~-.     ~- _
              |_____|          |_____|         ~ - . _ _~_-_
-->
