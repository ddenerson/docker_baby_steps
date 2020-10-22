# Docker

![0*rmv6pZTW2hfP2XYd](https://user-images.githubusercontent.com/33932398/96685464-85076600-1353-11eb-9f1c-a83e340eaf42.png)


## 1 - Managing images - download and delete

The goal of this exercise is to familiarize you with downloading and deleting images. In this exercise,
you'll focus on two popular applications, Jenkins and Apache.

## Instructions:

### Download the Images Jenkins and Apache

Use the following command: 

<pre><font color="#8AE234"><b>root@ddenerson</b></font>:<font color="#729FCF"><b>~/Documentos/Desenvolvimento/Docker</b></font>$ docker pull jenkins
latest: Pulling from library/jenkins
55cbf04beb70: Pull complete 
1607093a898c: Pull complete 
9a8ea045c926: Pull complete 
d4eee24d4dac: Pull complete 
c58988e753d7: Pull complete 
794a04897db9: Pull complete 
70fcfa476f73: Pull complete 
0539c80a02be: Pull complete 
54fefc6dcf80: Pull complete 
911bc90e47a8: Pull complete 
38430d93efed: Pull complete 
7e46ccda148a: Pull complete 
c0cbcb5ac747: Pull complete 
35ade7a86a8e: Pull complete 
aa433a6a56b1: Pull complete 
841c1dd38d62: Pull complete 
b865dcb08714: Pull complete 
5a3779030005: Pull complete 
12b47c68955c: Pull complete 
1322ea3e7bfd: Pull complete 
Digest: sha256:eeb4850eb65f2d92500e421b430ed1ec58a7ac909e91f518926e02473904f668
Status: Downloaded newer image for jenkins:latest
docker.io/library/jenkins:latest

<pre><font color="#8AE234"><b>root@ddenerson</b></font>:<font color="#729FCF"><b>~/Documentos/Desenvolvimento/Docker</b></font>$ docker pull httpd
latest: Pulling from library/httpd
bb79b6b2107f: Already exists 
26694ef5449a: Pull complete 
7b85101950dd: Pull complete 
da919f2696f2: Pull complete 
3ae86ea9f1b9: Pull complete 
Digest: sha256:b82fb56847fcbcca9f8f162a3232acb4a302af96b1b2af1c4c3ac45ef0c9b968
Status: Downloaded newer image for httpd:latest
docker.io/library/httpd:latest</pre>

### Check the images are present

List the two images that we downloaded:

<pre><font color="#8AE234"><b>root@ddenerson</b></font>:<font color="#729FCF"><b>~</b></font>$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
nginx               latest              f35646e83998        7 days ago          133MB
httpd               latest              3dd970e6b110        7 days ago          138MB
hello-world         latest              bf756fb1ae65        9 months ago        13.3kB
jenkins             latest              cd14cecfdb3a        2 years ago         696MB
</pre>

### Check to see how much disk space all of images combined are using

<pre><font color="#8AE234"><b>root@ddenerson</b></font>:<font color="#729FCF"><b>~</b></font>$ docker system df
TYPE                TOTAL               ACTIVE              SIZE                RECLAIMABLE
Images              4                   1                   896.9MB             896.9MB (99%)
Containers          1                   0                   0B                  0B
Local Volumes       0                   0                   0B                  0B
Build Cache         0                   0                   0B                  0B
</pre>


### Delete the Images

<pre><font color="#8AE234"><b>root@ddenerson</b></font>:<font color="#729FCF"><b>~</b></font>$ docker rmi httpd:latest 
Untagged: httpd:latest
Untagged: httpd@sha256:b82fb56847fcbcca9f8f162a3232acb4a302af96b1b2af1c4c3ac45ef0c9b968
Deleted: sha256:3dd970e6b110c8cbcec63e05a91e3cefd23c76a780fcb78c33979153f044b2d4
Deleted: sha256:92ed257f355234f3e6173699f2ef99363a5babec07a6b9178b2b1afb57214c55
Deleted: sha256:b57fd9052964b1f8e16ba5e3785018ba52de527c6aba686bb3845581ca4b77d7
Deleted: sha256:7c5691090fa42972426637baa64d47cc76a2af6a09423fbd4552e959595a17f7
Deleted: sha256:82996196e5b37bdac8de814bf831d8195211cd95e6ab9486d9684d762d57ec7a
</pre>

<pre><font color="#8AE234"><b>root@ddenerson</b></font>:<font color="#729FCF"><b>~</b></font>$ docker rmi jenkins:latest 
Untagged: jenkins:latest
Untagged: jenkins@sha256:eeb4850eb65f2d92500e421b430ed1ec58a7ac909e91f518926e02473904f668
Deleted: sha256:cd14cecfdb3a657ba7d05bea026e7ac8b9abafc6e5c66253ab327c7211fa6281
Deleted: sha256:9047d4817dd4203ae4d456888aa5355bc526d274713d6f168359ba61b85b6c00
Deleted: sha256:b6eeb6c0e550e93a8b6293a35b2a68931a2af1d21cf8fe8c53bd412359433fdc
Deleted: sha256:54a9d685504efad152c1032f37f76ee95bae30607f68bd0ff48a095ebec5d820
Deleted: sha256:0b5e1c633ad7fa60f5185ff00ccbff9af3608ba336dc7c01868f9cd0dd8a7137
Deleted: sha256:0373335894092868f06432433f14881bd6f09d851931d6e5090601a64e0466f3
Deleted: sha256:b4e8f84d7b87e7994e49a190bc35871b23f76d9cab573308fa1ae7401c50dcc6
Deleted: sha256:cde912e85b12d50e9e4d056ad3c8cb35853c60291dbe4b319dcd80bcd2ef243c
Deleted: sha256:8062b94ccb384de40b6777515f21b895be64218c5296bac3ee6db2ed4c5db9fe
Deleted: sha256:a3411e0c109af31befac78bcbd2aba26f893717f645df8d4828bf29772417bc0
Deleted: sha256:fb1cc4fe4174cb86f9614cf9ee4c6cecad4c7f0c04ca52c95fd1a7d0d79471e8
Deleted: sha256:1fe73f13106502d5c58cc444a71738c518b341fd667fc26058f3e473a3cc559f
Deleted: sha256:d3898f75e7b8a2a7e45bfdd351a00c4ad95b743861860635d702378fd073771d
Deleted: sha256:46ddeaf1e1efd81fd6cad11c44af4e4ba71cbab32b75f60f8647f025a8874315
Deleted: sha256:4e9ac8670c1ea60c504c1dc22e38a177afd782a48e17e81e06ecf60a1c8f4ef0
Deleted: sha256:76dc20911db5ba40907269c70aa4ef7caf207ea4aa23818b8db2ff83ba74e1e4
Deleted: sha256:b4ff564f2a75c2bc85c8eda2928ec73b13809416658f949d2b55fa24448c08b1
Deleted: sha256:2d9c829ae3f7ff3e148e5c7c3a1cf378b0f90b79035e2fe9a8d78c63ccde4c89
Deleted: sha256:b1ae7168c6f3e061aa3943740ec3ceaf8e582dc65feab31d2b56d464a5062d59
Deleted: sha256:4a495dbc04bd205c728297a08cf203988e91caeafe4b21fcad94c893a53d96dc
Deleted: sha256:3b10514a95bec77489a57d6e2fbfddb7ddfdb643907470ce5de0f1b05c603706
</pre>






