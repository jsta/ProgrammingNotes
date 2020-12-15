## Updating software

These are the things I do every other week to keep my computers'
software up to date.

```
sudo apt-get update
sudo apt-get upgrade

R -e 'update.packages(ask=FALSE)'
R -e 'update.packages(ask=FALSE, checkBuilt=TRUE)'

rvm get stable
gem update

conda update conda
conda update anaconda

npm update npm -g
npm update -g
npm install -g npm@latest

sudo tlmgr update --self
sudo tlmgr update --all
```
