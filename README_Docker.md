
<h1>Install Docker and Setup Docker Environment</h1>
Docker Machine is a tool that lets you install Docker Engine on virtual hosts:
``` bash
docker-machine start
```
``` bash
docker-machine env
```
``` bash
eval $(docker-machine env)
```
Get the IP address:
```
docker-machine ip default
```
<h2>Files Structure</h2>
1. Dockerfile
2. model (folder)
	a) executable script:
		1) score.r
		2) score.py
	b) requirements.txt (optional) contains the packages needed for pip install for python script
3. sample-data (folder)
s
<b>Deploy a model</b>
