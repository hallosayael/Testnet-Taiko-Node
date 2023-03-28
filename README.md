# Testnet-Taiko-Node
<p align="center">
  <img height="150" height="auto" src="https://taiko.xyz/_next/image?url=%2Fimages%2Flogotype-black.png&w=128&q=75">
</p>

# SIMPLE TAIKO NODE (TESTNET)

## 1. Ikhtisar

Panduan ini akan memandu Anda melalui proses pengoperasian node Taiko melalui simple-taiko-node (terbuka di tab baru). Anda akan sanggup untuk:

- Jalankan node Taiko dengan mudah dari baris perintah di Windows, Mac, dan Linux.
- Jalankan node Taiko secara teratur atau sebagai pembuktian.
- Lihat dasbor Grafana (terbuka di tab baru) yang menampilkan status node.

## 2. Spesifiksi Minimal

Berikut adalah persyaratan **minimum** untuk menjalankan node TAIKO:

-	CPU with 2+ cores
-	4GB RAM
-	1TB free storage space to sync the Mainnet
-	8 MBit/sec download Internet service


# Clone simple-taiko-node

```
git clone https://github.com/taikoxyz/simple-taiko-node.git
```

Masuk ke folder simple-taiko-node

```
cd simple-taiko-node
```

# Configure your node (required)

First, copy the .env.sample to a new file .env:

```
cp .env.sample .env
```
Next, open the .env file in your preferred text editor (for Linux):

```
vim .env
```
Finally, set the following environment variables:

-	L1_ENDPOINT_HTTP
-	L1_ENDPOINT_WS

# Start a node

Make sure Docker is running and then run the following command to start the node. If you want to run it in the background, please add the -d flag (docker compose up -d).

```
docker compose up
```

To run the node in the background (detached mode), use the -d flag:
```
docker compose up -d
```

# Stop a node

This command shuts down the node, but will keep all volumes, so next time you restart the node, it won't need to synchronize from the genesis again.

```
docker compose down
```

# Remove a node

These commands will completely remove the node by removing all volumes used by each container:

```
docker compose down -v
rm -f .env
```

# Update a node

Update the simple-taiko-node Docker images:

```
docker compose pull
```

# View the node's logs

View all logs

```
docker compose logs -f
```

# View the node's status dashboard

A Grafana (opens in a new tab) dashboard with a Prometheus (opens in a new tab) datasource is also included to display the L2 execution engine's real time status. You can visit it at http://localhost:3000/d/L2ExecutionEngine/l2-execution-engine-overview?orgId=1&refresh=10s (opens in a new tab).

<p>
<img src="https://user-images.githubusercontent.com/104078303/207779788-65d28e44-828e-491a-86a1-d8d9fc2ba81b.png">
</p>


## Source

https://taiko.xyz/docs/guides/run-a-node

