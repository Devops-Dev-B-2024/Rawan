3.
a-
$  docker run -it --rm -d -p 8080:80 --name web nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
8a1e25ce7c4f: Pull complete
e78b137be355: Pull complete
39fc875bd2b2: Pull complete
035788421403: Pull complete
87c3fb37cbf2: Pull complete
c5cdd1ce752d: Pull complete
33952c599532: Pull complete
Digest: sha256:6db391d1c0cfb30588ba0bf72ea999404f2764febf0f1f196acd5867ac7efa7e
Status: Downloaded newer image for nginx:latest
c8d5dabd604baaf7da097c6763a14dbdc9a3e2d52597f53ae7d34df81674fd11
c-
 après la création de html/index.html:
$ docker run -d -p 8080:80 --name web -v /${PWD}/TP2/html:/usr/share/nginx/html nginx
3628c4a8572f9ca870f3caedd1d5d2360b828893b6672e444ddea086214e39f5


-*-*-*-*-*-*--*-**-*-*-*-*-*-*--**-*--*-**-*-*-*-*--**-*-*-*-*-*-*-**--*-*-*-*-**-*--**--*-*-*-*-*-*-*


4.
creation dockerfile
-------------------------------------

$ docker build -t webserver .
[+] Building 21.0s (7/7) FINISHED                                                                     docker:default
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 101B                                                                            0.0s 
 => [internal] load metadata for docker.io/library/nginx:latest                                                 1.0s 
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s 
 => [internal] load build context                                                                               0.0s 
 => => transferring context: 229B                                                                               0.0s 
 => [1/2] FROM docker.io/library/nginx:latest@sha256:6db391d1c0cfb30588ba0bf72ea999404f2764febf0f1f196acd5867  18.8s 
 => => resolve docker.io/library/nginx:latest@sha256:6db391d1c0cfb30588ba0bf72ea999404f2764febf0f1f196acd5867a  0.0s 
 => => sha256:52478f8cd6a142fd462f0a7614a7bb064e969a4c083648235d6943c786df8cc7 2.29kB / 2.29kB                  0.0s 
 => => sha256:8a1e25ce7c4f75e372e9884f8f7b1bedcfe4a7a7d452eb4b0a1c7477c9a90345 29.12MB / 29.12MB               15.1s 
 => => sha256:e78b137be3552e1f36d84cb01c533a23febe4c48f6fcdff5d5b26a45a636053b 41.39MB / 41.39MB               10.5s 
 => => sha256:39fc875bd2b2e4f867e8e5cc5ad43bd5d6650ddeaf8c28b04f374f7fbca085f3 624B / 624B                      2.1s 
 => => sha256:6db391d1c0cfb30588ba0bf72ea999404f2764febf0f1f196acd5867ac7efa7e 9.85kB / 9.85kB                  0.0s 
 => => sha256:92b11f67642b62bbb98e7e49169c346b30e20cd3c1c034d31087e46924b9312e 7.02kB / 7.02kB                  0.0s 
 => => sha256:035788421403127b57e688a82706198331f06545a955b526f89f2bf53f52b078 954B / 954B                      2.7s
 => => sha256:87c3fb37cbf2f763f67f3b270aa0785ca05a2caedac399b4bfeedfd0ccd77d87 392B / 392B                      2.9s
 => => sha256:c5cdd1ce752da415a6563d9432e1ee718b2f4ba353ee2bb7c8ce2aa78d5b4ee1 1.21kB / 1.21kB                  3.2s
 => => sha256:33952c5995320e59a81112f411bfb02e097562a72c12e85828da51132ace47cd 1.40kB / 1.40kB                  3.9s
 => => extracting sha256:8a1e25ce7c4f75e372e9884f8f7b1bedcfe4a7a7d452eb4b0a1c7477c9a90345                       2.1s
 => => extracting sha256:e78b137be3552e1f36d84cb01c533a23febe4c48f6fcdff5d5b26a45a636053b                       1.1s
 => => extracting sha256:39fc875bd2b2e4f867e8e5cc5ad43bd5d6650ddeaf8c28b04f374f7fbca085f3                       0.0s
 => => extracting sha256:035788421403127b57e688a82706198331f06545a955b526f89f2bf53f52b078                       0.0s
 => => extracting sha256:87c3fb37cbf2f763f67f3b270aa0785ca05a2caedac399b4bfeedfd0ccd77d87                       0.0s 
 => => extracting sha256:c5cdd1ce752da415a6563d9432e1ee718b2f4ba353ee2bb7c8ce2aa78d5b4ee1                       0.0s 
 => => extracting sha256:33952c5995320e59a81112f411bfb02e097562a72c12e85828da51132ace47cd                       0.0s 
 => [2/2] COPY ./html/index.html /usr/share/nginx/html/                                                         1.0s 
 => exporting to image                                                                                          0.0s 
 => => exporting layers                                                                                         0.0s 
 => => writing image sha256:84ae364cae07892926dde5ede3d60e64633e63037d1f1bf8b141e20469434dcc                    0.0s 
 => => naming to docker.io/library/webserver                                                                    0.0s 

View build details: docker-desktop://dashboard/build/default/default/ilaijhk6n72rodvyi0vhmpeg0