# docker-reivew
- DockerでRE:VIEWを動かす．

## 手順
```bash
git clone git@github.com:solareenlo/docker-review.git
cd docker-review
sudo docker pull vvakame/review:4.0
sudo docker-compose run --rm review review-init test
sudo chown -R solareenlo:solareenlo test
cp docker-compose.yml Dockerfile test
sudo docker-compose run --rm review rake pdf
sudo docker-compose run --rm review rake epub
```

## 書き方
- https://github.com/kmuto/review/wiki
