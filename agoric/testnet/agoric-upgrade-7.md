<p style="font-size:14px" align="right">
<a href="https://kjnodes.com/" target="_blank">Visit our website <img src="https://user-images.githubusercontent.com/50621007/168689709-7e537ca6-b6b8-4adc-9bd0-186ea4ea4aed.png" width="30"/></a>
<a href="https://discord.gg/QmGfDKrA" target="_blank">Join our discord <img src="https://user-images.githubusercontent.com/50621007/176236430-53b0f4de-41ff-41f7-92a1-4233890a90c8.png" width="30"/></a>
<a href="https://kjnodes.com/" target="_blank">Visit our website <img src="https://user-images.githubusercontent.com/50621007/168689709-7e537ca6-b6b8-4adc-9bd0-186ea4ea4aed.png" width="30"/></a>
</p>

<p style="font-size:14px" align="right">
<a href="https://hetzner.cloud/?ref=y8pQKS2nNy7i" target="_blank">Deploy your VPS using our referral link to get 20€ bonus <img src="https://user-images.githubusercontent.com/50621007/174612278-11716b2a-d662-487e-8085-3686278dd869.png" width="30"/></a>
</p>

<p align="center">
  <img height="100" height="auto" src="https://user-images.githubusercontent.com/50621007/167032367-fee4380e-7678-43e0-9206-36d72b32b8ae.png">
</p>

# Chain upgrade to agoric-upgrade-7
## (OPTION 1) Manual upgrade
Once the chain reaches the upgrade height, you will encounter the following panic error message:\
`ERR UPGRADE "agoric-upgrade-7" NEEDED at height: 146039`
```
cd $HOME && rm $HOME/ag0 -rf
git clone https://github.com/Agoric/ag0
cd ag0
git checkout agoric-upgrade-7
make build
. $HOME/.bash_profile
cp $HOME/ag0/build/ag0 /usr/local/bin
systemctl restart agoricd && journalctl -fu agoricd -o cat
```

!!! DO NOT UPGRADE BEFORE CHAIN RECHES THE BLOCK `146039`!!!

### (OPTION 2) Automatic upgrade
As an alternative we have prepared script that should update your binary when block height is reached
Run this in a `screen` so it will not get stopped when session disconnected 😉
```
wget -O agoric-upgrade-7.sh https://raw.githubusercontent.com/kj89/testnet_manuals/main/agoric/testnet/tools/agoric-upgrade-7.sh && chmod +x agoric-upgrade-7.sh && ./agoric-upgrade-7.sh
```