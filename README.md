
[![](https://images.microbadger.com/badges/version/bigg01/helm-s2i-centos7.svg)](https://microbadger.com/images/bigg01/helm-s2i-centos7 "Get your own version badge on microbadger.com")



### localtest
```sh
docker build -t bigg01/helm-s2i-centos .
s2i build -e CHART=golang-ex  ../go-s2i-centos7/helm bigg01/helm-s2i-centos test
```