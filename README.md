# House Automation
These are the steps required for preparing data, training the module and testing it. This module can detect different hand signs which each mean a different house item, like turning on or off the lights/fan or moving the curtains up or down.

![Lights Working](https://github.com/jpgarciao/House-Automation/assets/138504441/6a14b28d-9e8a-4b32-bced-c62ea8349ad1)

This image shows the lights task working.

## The Algorithm
To begin you have to set up the Jetson Nano.
1. First you have to create a SSH connection with your nano.
2. Next you will want to create a directory called **nvdli-data** using the command, `mkdir -p ~/nvdli-data`
3. Then for easier access you will create a reusable script to run the **docker container** using the command, `echo "sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.2-r32.7.1" > docker_dli_run.sh`
4. Now that you have the script, run, `chmod +x docker_dli_run.sh`, which is a command that makes the script executable.
5. After you've done that, run the script with the command, `./docker_dli_run.sh`.
6. Once the docker container has finished downloading you will find a line that says *allow 10 sec for JupyterLab to start @ http://xxx.xxx.xxx.xxx:8888 (password dlinano)*, copy the link that contains what is your ip adress and access jupytrlab using the password that is given to you by the line.
7. Once you are inside jupyterlab, you will access the classification folder and open the classification_interactive.ipyn where everything is already set up for you.

## Running this project

1. Add steps for running this project.
2. Make sure to include any required libraries that need to be installed for your project to run.

[View a video explanation here](video link)

Link for using different text types in the readme file https://www.markdownguide.org/cheat-sheet/
