# ESP-IDF `MAC` Install

## Step 1. Install Prerequisites
In order to use ESP-IDF with the ESP32, you need to install `CMake, ccache, python3` and `Ninja`
- Check if your Mac has Homebrew or MacPorts.
```bash
brew --version
port version
```
- If you have `HomeBrew`, you can run:
```bash
brew install cmake ninja dfu-util
brew install ccache
brew install python3
```
- If you have `MacPorts`, you can run:
```bash
sudo port install cmake ninja dfu-util
sudo port install ccache
sudo port install python38
```
## Step 2. Get ESP-IDF
Espressif official [ESP-IDF repository](https://github.com/espressif/esp-idf)
```bash
mkdir development
cd development
git clone -b v5.4 --recursive https://github.com/espressif/esp-idf.git
```
- install the tools used by ESP-IDF. 
```bash
cd esp-idf
./install.sh esp32
./install.sh esp32,esp32s2
./install.sh all
```
or
```bash
cd esp-idf
./install.fish esp32
./install.fish esp32,esp32s2
./install.fish all
```
- Alternative File Downloads.
```bash
export IDF_GITHUB_ASSETS="dl.espressif.com/github_assets"
./install.sh
```

Step 4. Set up the `Environment Variables`
In the terminal where you are going to use ESP-IDF, run:
```bash
$HOME/development/esp/export.sh
```
or for fish (supported only since fish version 3.0.0):
```bash
$HOME/development/esp/export.fish
```
- create an alias for executing export.sh (optional)
```bash
alias get_idf='. $HOME/development/esp/export.sh'
```
```bash
source ~/.bashrc
```

