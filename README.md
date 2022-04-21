# StarkNet node
sudo apt update && sudo apt upgrade -y
sudo apt install curl git build-essential libgmp-dev pkg-config screen libssl-dev python3.8-venv python3-pip python3-dev -y
pip3 install fastecdsa
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
cargo --version
STEP 2
screen -S 1
git clone --branch v0.1.8-alpha https://github.com/eqlabs/pathfinder.git
cd pathfinder/py
python3 -m venv .venv
source .venv/bin/activate
PIP_REQUIRE_VIRTUALENV=true pip install --upgrade pip
PIP_REQUIRE_VIRTUALENV=true pip install -r requirements-dev.txt
cargo run --release --bin pathfinder -- --ethereum.url <YOUR URL Alchemy>
