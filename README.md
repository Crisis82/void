# Crisis82 Void XBPS Repository

Personal Void Linux package repository for missing xbps packages

## Install

```sh
echo 'repository=https://github.com/Crisis82/void/releases/download/repository-x86_64' | sudo tee /etc/xbps.d/crisis82.conf
```

On first sync, accept the repository fingerprint prompt to import the signing key.

Then install packages as usual, like

```sh
sudo xbps-install discord
```

## Supported packages

- cavaii
- calci
- ags
- discord
- webcord
- teams-for-linux
- spotify

## Notes

XBPS packages need a signature to be installed, which can be added by creating a GitHub secret `PRIV_KEY` with the following setup:

```sh
ssh-keygen -t rsa -b 4096 -m PEM -f ~/.ssh/xbps-repo-signing -N ''
cat ~/.ssh/xbps-repo-signing | gh secret set PRIV_KEY --repo Crisis82/void
```
