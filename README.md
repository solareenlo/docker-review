# docker-reivew
- DockerでRE:VIEWを動かす．

## 手順
```bash
git clone git@github.com:solareenlo/docker-review.git
cd docker-review
sudo docker pull vvakame/review:4.0
// docker-compose を使って最初の元データ群を作成する
sudo docker-compose run --rm review review-init test
// docker を使って最初の元データ群を作成する
sudo docker run --rm --mount type=bind,source=$(pwd),target=/work vvakame/review:4.0 /bin/sh -c "cd /work && review-init hello"
// 作った最初のデータ群の所有権を変更して
sudo chown -R solareenlo:solareenlo test
// docker-compose フィアルと Dockerfile をコピーする
cp docker-compose.yml Dockerfile test
// 最初の元データ群の test ディレクトリに移動して、作文する
cd test
// docker-compose を使って pdf ファイルを作成する
sudo docker-compose run --rm review rake pdf
// docker を使って pdf ファイルを作成する
sudo docker run --rm --mount type=bind,source=$(pwd),target=/work vvakame/review:4.0 /bin/sh -c "cd /work && rake pdf"
// docker-compose を使って epub ファイルを作成する
sudo docker-compose run --rm review rake epub
// docker を使って epub ファイルを作成する
sudo docker run --rm --mount type=bind,source=$(pwd),target=/work vvakame/review:4.0 /bin/sh -c "cd /work && rake epub"
```

## 書き方
- https://github.com/kmuto/review/wiki
- [Re:VIEWチートシート](https://gist.github.com/erukiti/c4e3189dda179a0f0b73299fb5787838)

## References
- https://github.com/vvakame/docker-review
- https://github.com/vvakame/docker-review/blob/master/doc/windows-review.md
- https://gist.github.com/erukiti/c4e3189dda179a0f0b73299fb5787838
