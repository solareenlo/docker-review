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
- [Re:VIEWチートシート](https://gist.github.com/erukiti/c4e3189dda179a0f0b73299fb5787838)

## References
- https://github.com/vvakame/docker-review
- https://github.com/vvakame/docker-review/blob/master/doc/windows-review.md
- https://gist.github.com/erukiti/c4e3189dda179a0f0b73299fb5787838
