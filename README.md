# Muon-Mainnet
### Update & docker kurulum 
```
sudo apt-get update && sudo apt install jq git && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin && sudo apt-get install docker-compose-plugin
```
### Eskisi varsa silmek için
```
docker stop muon-node mongo redis
docker rm muon-node mongo redis
```
### Kurulum için gerekli dosyaları çekelim
```
curl -o docker-compose.yml https://raw.githubusercontent.com/muon-protocol/muon-node-js/pion/docker-compose-pull.yml
```
### Kurulum
```
docker compose pull
```
### Çalıştırma
```
docker compose up -d
```
yada olmassa
```
docker-compose up -d
```
### Gerekli bilgileri alma
Not: Biraz bekledikten sonra çıktı verecek kaydedin portalda lazım olacak.
```
curl http://localhost:8012/status
```
![image](https://github.com/molla202/Muon-Mainnet/assets/91562185/afe32338-ad35-4e0d-9ba7-5329dab48309)

* Kalan işlemler panelden hallediliyor. panel hakkında grubdan yardım alabilirsiniz. `hayırlı olsun`

### Yedek alma
not: ana klasöründe backup.json dosyası oluşacak bunun yedeğini pcmize alalım.
```
docker exec -it muon-node ./node_modules/.bin/ts-node ./src/cmd/index.ts keys backup > backup.json
```
```
cat backup.json
```
