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
Now that you are in, follow these steps to correctly run the project.
1. First you will run the cells under the **camera** section.
2. After, in the **task** section you will want to change the variable called *TASK* by making the current task into a comment using the *#*, after you've made it into a comment, create a variable also called *TASK* and make it equal house, it should look like this: `TASK = 'house'`
3. While still in the **task** section, you will make the current *CATEGORIES* into a comment like you've done with *TASK* and make a new variable called CATEGORIES which equals *['fan','lights','ac','curtains']*, it should look like this: `CATEGORIES = ['fan','lights','ac','curtains']`
Here is how it should look:
![Categories changing tutorial](https://github.com/jpgarciao/House-Automation/assets/138504441/976492ea-f953-4fad-a83e-299587c3d90a)
4. Now run all cells in the **task** section.
5. After this run all cells in the sections from the **Data Collection** section to the **Training and Evaluation** section to create all the widgets for the project.
6. After making the widgets you will run the cell under the **Display the Interactive Tool!** section to create the workplace.
7. Once you are in the workplace, choose a hand sign for each category of the task and take 80 pictures of just that hand sign in a background, refrain from showing your face so the camera only looks for the hand sign and not your face.
8. Now train the model for about 20-30 epochs.
9. Once it's done training, try out the model and see if it works, if it works it should look like this: 
![Fan Working](https://github.com/jpgarciao/House-Automation/assets/138504441/dd68ccf8-3ac1-47a2-8d82-0d6d696e39f1)


[View a video explanation here](https://www.youtube.com/watch?v=cay_tClT7ww)
