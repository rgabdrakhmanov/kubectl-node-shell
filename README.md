# kubectl node-shell

*NOTE: this is a fork of https://github.com/kvaps/kubectl-node-shell *(formerly known as **kubectl-enter**)* made for my own purpose and modifications, hence it lacks some features of the original*

Start a root shell in the node's host OS running.

## Installation

using curl:

```bash
curl -LO https://github.com/rgabdrakhmanov/kubectl-node-shell/raw/master/kubectl-node_shell
chmod +x ./kubectl-node_shell
sudo mv ./kubectl-node_shell /usr/local/bin/kubectl-node_shell
```

## Usage

```bash
# Get standard bash shell
kubectl node-shell <node>

# Execute custom command
kubectl node-shell <node> -- echo 123

# Use stdin
cat /etc/passwd | kubectl node-shell <node> -- sh -c 'cat > /tmp/passwd'

# Run oneliner script
kubectl node-shell <node> -- sh -c 'cat /tmp/passwd; rm -f /tmp/passwd'
```

*You need to be able to start privileged containers for that.*
