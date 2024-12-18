# SixGPT Miner
This is the official SixGPT miner.

# About

SixGPT is a decentralized synthetic data generation platform built on the Vana network. We empower users by giving them ownership of their data and enabling them to earn from it.

The SixGPT Miner is a software package which allows users to contribute data they generate for wikipedia question-answer based tasks to the network for rewards.
In the future, we will support other tasks such as chatbot conversations, image captioning, etc.

## Prerequisites
(1) install docker on your machine. (https://docs.docker.com/engine/install/)

(2) Fund your wallet with at least 0.1 $VANA

(3) Login with this wallet on sixgpt.xyz


## Run the miner:
Clone the repository:
```
git clone https://github.com/sixgpt/miner.git
cd miner
```

### Run the miner with CPU
Create an .env file. Make sure your Vana Private key is set to your wallet private key (0x...)
```
VANA_PRIVATE_KEY=abcdefabcef
VANA_NETWORK=mainnet
OLLAMA_API_URL=http://ollama:11434/api
```
Run the miner:

```
docker-compose up -d
```
Stop the miner:

```
docker-compose down
```
Check miner logs:
```
docker-compose logs -f
```

### Run the miner with more advanced options
```
chmod +x run_sixgpt.sh
./run_sixgpt.sh
```

## Notes
- You must have logged into sixgpt.xyz with your wallet before running the miner
- Make sure the wallet associated with your vana private key has enough $VANA balance on the desired network (at least 0.1)

## Additional Notes on Handling GPU Detection
- [ollama github](https://github.com/ollama/ollama)
- [ollama docker](https://hub.docker.com/r/ollama/ollama)
- NVIDIA GPUs: Ensure that you have the NVIDIA Container Toolkit installed to enable GPU support in Docker. You can follow the installation guide [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html).
- AMD GPUs: For AMD, ensure that the ROCm (Radeon Open Compute) stack is installed and configured correctly. More details can be found on the official ROCm documentation [ROCm (Radeon Open Compute) stack](https://rocm.docs.amd.com/en/latest/).