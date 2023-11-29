
## Building graminized Docker image

1. Chekout the below gsc branch
```bash
   git clone https://github.com/amathew3/gsc.git
   git checkout besu_fix 
```

2. Pull the besu official Docker image:
```bash
docker pull hyperledger/besu:latest
```

3. Graminize the Docker image using `gsc build`:
```bash
cd gsc
./gsc build --insecure-args -b release hyperledger/besu:latest Examples/besu/besu.manifest
```

4. Sign the graminized Docker image using `gsc sign-image`:
```bash
./gsc sign-image hyperledger/besu:latest enclave-key.pem
```

## Running the gsc besu image.
```bash
docker run -it --device /dev/sgx_enclave gsc-hyperledger/besu:latest
```
