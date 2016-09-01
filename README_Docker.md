
<h1>Deployment Using Docker</h1>

<h2>Files Structure</h2>
1. Dockerfile
2. model (folder)
	- executable script (options):
		* score.r
		* score.py
	- requirements.txt (optional) contains the packages needed for pip install for python script
3. sample-data (folder)
	- input.json (optional) for local testing
	- metadata.json: contains attributes names used for model and metrics (results)
	- model file (options): 
		* configuration.json
		* model.rds
		* csv file (ex: contains diagnosis, drug mismatch rules)

<h2>Create a Dockerfile</h2>
[Absolute README link](https://github.com/KenSciML/ModelCore/README.md)

<h2>Deploy a Model</h2>
<h3> Set up the docker enviroment </h3>
Since all models docker settings are based on the modelcore, need to pull the kensci modelcore docker images before building the image 

Every Dockerfile needs to include lines below
```bash
FROM kensci/modelcore:latest
MAINTAINER KenSci
```
```bash 
>>> docker pull kensci/modelcore:latest
```

<h3> Build the Dockerfile </h3>
Direct to the same folder where the dockerfile locates and build the docker image have the tag on it 

```bash
>>> docker build -t kensci/dupmodel:latest .
```
Display the images:
```
>>> docker images
```
``` bash
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
kensci/dupmodel     latest              47cd0c5e4369        4 hours ago         710.7 MB
kensci/clustering   latest              2c80f707bf1e        22 hours ago        763.6 MB
kensci/modelcore    latest              07d9d958b344        22 hours ago        462.8 MB
ubuntu              latest              f8d79ba03c00        2 weeks ago         126.4 MB
```

<h3> Deploy a model</h3>
Example:
```
>>> docker run -p 3333:80 -ti -v /Users/XinheWang/ModelBank/DuplicateDetection/sample-data:/tmp/sample-data kensci/dupmodel:latest deploy /tmp/sample-data/configuration.json /tmp/sample-data/metadata.json
```

use -v to add data volume to a container, mount source code inside a container
-p expose the port number to 3333

<h3> Test </h3>
	- API get the metadata of a model: local ip address/docker-machine default ip:3333/metadata
	- API get the score  (post api): local ip address/docker-machine default ip:3333/score





