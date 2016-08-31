
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

<b>Deploy a Model</b>
1. Set up the docker enviroment 
2. Build the Dockerfile


