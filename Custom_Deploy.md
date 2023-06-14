# Deployment Notes Digital Slide Archive for KC4.0 UTP

## Basic Installation
- Clone the Digital Slide Archive repo:
`git clone https://github.com/DigitalSlideArchive/digital_slide_archive.git`
- Deploy with docker
`cd devops`
- If the image has not been build or you are deploying for the first time, build the project with the following command:
`./deploy.sh start --build`
- Then start the services:
`./deploy.sh start`
- Now, the application can be accessed at: http://localhost:8080/
## Deploy on custom port

- Navigate to the deploy folder:
`cd devops`
- To deploy at custom `PORT_NUMBER` e.g 9090, add the following lines at line 41 in the file `deploy.sh`:
`OPTS+=(-p PORT_NUMBER)`
`OPTS+=(--worker-api-url "http://girder:PORT_NUMBER/api/v1")`
- Then, build the project and start the services
`./deploy.sh start --build`
- Now, the application can be accessed at: http://localhost:`PORT_NUMBER`/ (e.g http://localhost:9090/)
## Deploy with Custom UI
- Clone the HistomicsUI repo:
`git clone https://github.com/DigitalSlideArchive/HistomicsUI.git`
- Navigate to `histomicsui/web_client` then conduct your custom changes
- Navigate back to the dsa folder e.g `cd ~/dungpt/DigitalSlideArchive/devops`
- Change the default `HISTOMICS_SOURCE_FOLDER` to point at your local folder:
`export HISTOMICS_TESTDATA_FOLDER=~/dungpt/HistomicsUI`