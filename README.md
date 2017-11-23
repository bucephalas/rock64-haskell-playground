# About 
This is a playground for haskell on the rock64 platform

This is an example project demonstrating a servant example service on the aarch64 
architecture using the Rock64 Single Board Computer.

# Links
### Rock64 SBC:
http://wiki.pine64.org/index.php/ROCK64_Main_Page

### Servant Server Example
https://github.com/haskell-servant/servant/tree/master/servant-server/example

### Debian image for Rock64
https://github.com/ayufan-rock64/linux-build/releases

# Setup Instructions
1. Download & copy to emmc or sd release 5.10 Debian stretch image - https://github.com/ayufan-rock64/linux-build/releases/download/0.5.10/stretch-minimal-rock64-0.5.10-118-arm64.img.xz

2. Log in - fix to use IPv4 was needed to install Debian packages - https://unix.stackexchange.com/a/100887
  2.1 configure hostname with nmtui - `sudo apt-get install nmtui`, `sudo nmtui` to configure with hostname, eg. rock64, and verify that rock64.local is available on network.

3. Install ghc, cabal and zlib - sudo apt-get install ghc cabal-install zlib1g-dev 
  3.1 ghc is unregistered but seems to work well, ghci as well

4. `cabal install servant-server` - required a reboot due to network issue, otherwise installed 

5. `cabal build` this package & run `dist/build/greet/greet`.  in browser check http://rock64.local:8080/hello/peter



