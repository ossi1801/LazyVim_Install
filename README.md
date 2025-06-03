# LazyVim Install
quick guide for (myself in) linux

## 1. Neovim
```
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux-x86_64.tar.gz
```
```
sudo rm -rf /opt/nvim
```
```
sudo tar -C /opt -xzf nvim-linux-x86_64.tar.gz
```
#### 1.1 Then add this to your shell config (~/.bashrc, ~/.zshrc, ...):
```
export PATH="$PATH:/opt/nvim-linux-x86_64/bin"
```
#### 1.2 Reload .bashrc:
```
. ~/.bashrc
```
#### or
```
source ~/.bashrc
```
#### 1.3 Test nvim
```
nvim
```
## 2. LazyVim

#### 2.1 Make a backup of your current Neovim files:
```
# required
mv ~/.config/nvim{,.bak}

# optional but recommended
mv ~/.local/share/nvim{,.bak}
mv ~/.local/state/nvim{,.bak}
mv ~/.cache/nvim{,.bak}
```
#### 2.2 Clone the starter
```
git clone https://github.com/LazyVim/starter ~/.config/nvim
```

#### 2.3 Remove the .git folder, so you can add it to your own repo later
```
rm -rf ~/.config/nvim/.git
```
#### 2.4 Start Neovim (lazyvim)!

```
nvim
```

##### It is recommended to run :LazyHealth after installation. This will load all plugins and check if everything is working correctly.

#### You can install your language based build tools (if you have not already) that can help the LSP:s to work properly ex. (in ubuntu)

#### C# sdk, runtime
```
sudo apt-get update && sudo apt-get install -y dotnet-sdk-8.0
sudo apt-get update && sudo apt-get install -y aspnetcore-runtime-8.0
sudo apt-get install -y dotnet-runtime-8.0
```
#### C++ essentials
```
sudo apt update && sudo apt install build-essential
```

