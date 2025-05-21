# podUTXOracle
UTXOracle port using podman with start9 node https://utxo.live/oracle/

ref on using bitcoin-cli: https://docs.start9.com/0.3.5.x/user-manual/container-access#container-access

## Useage:

 ssh into your start9 node
```bash
curl -O https://raw.githubusercontent.com/citizenanalog/podUTXOracle/refs/heads/main/podUTXOracle.py
```
```bash
python3 podUTXOracle.py
```
HTML files will be created in the working directory. Copy them back to your machine to view for now...

## Tips

Before running `podUTXOracle.py`, use these commands to verify your environment and troubleshoot common issues. These steps ensure your Bitcoin node, Python, and Podman are correctly set up.

### Verify the Bitcoin Node
Check if the Bitcoin node in the `bitcoind.embassy` container is running and responsive by retrieving the current block count:

```bash
sudo podman exec -it bitcoind.embassy bitcoin-cli getblockcount
```
## Check Python 3 Version
Ensure Python 3.6 or higher is installed, as podUTXOracle.py relies on modern Python features:
```bash
python3 --version
```
## Permission
You may need to modify block folder permissions
```bash
sudo chmod -R o+rx /embassy-data/package-data/volumes/bitcoind/data/main/blocks
```


