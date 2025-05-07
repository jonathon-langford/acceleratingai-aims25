# Accelerating Machine Learning
Welcome to the "Accelerating Machine Learning" course at AIMS 2025. This repository will store all of the course contents, and provide information on how to access the relevant notebooks.

The course requires access to OneAPIs FPGA codebase. To avoid a lengthy (and memory-intensive) installation process, we have set up a Docker container with the relevant libraries on Google Cloud Virtual Machines (VM). This VM will only stay active for a few days after the course due to running costs. The Google Colab link below provides a portal to the course notebook within the Docker container. 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1s2pALSzd1E-5aIZyLkkYQLf6hDc1k-Ag?usp=sharing)

You will need to input the VM IP address, port and jupyter token which can be found in the Google Sheets link below. Please use the VM as directed by the course leader. Note your progress is only saved on the VM that you are using i.e. if you switch machines then your progress will be lost. If (for some reason) one of the machines goes down, we will need to reload the Jupyter server. In this case, we will update the information in the Google Sheets and you will need to reload the link in the Google Colab portal.

Google Sheets link: [https://docs.google.com/spreadsheets/d/1La978EN-W2NXJsB4ocPxPl7cBZJCzdpCRqx2_BtFD5E/edit?usp=sharing]

After entering the details and clicking on the link provided in the Google Colab, a new browser window will open. Please enter the folder with your name and open the `hls4ml_introduction.ipynb` notebook.

## Course assessment
The notebook contains a number of assessed questions (highlighted in red) throughout. Please submit your responses to these questions via the following Google Forms: [https://forms.gle/2rugKQ1gvNbPTBwn9].

## Post-course 
If you find yourself inspired by the course, you can install all the necessary dependencies locally. Everything has been nicely containerized in a Docker image.

* Install Docker on your machine (if not done already). ChatGPT will help with the instructions.

* Clone this git repository, move to the directory and build the Docker image:
```
git clone https://github.com/jonathon-langford/acceleratingai-aims25.git
cd acceleratingai-aims25
docker build -t oneapi-hls4ml-2025 --build-arg user=$USER .
```

* Run the docker image, making sure that the container has access to your home folder (-v):
```
docker run -p 127.0.0.1:8080:8080 -v /home/$USER/:/home/$USER/local -it oneapi-hls4ml-2025
```

* Move to your working directory (change the path accordingly), and start a jupyter session:
```
cd /home/$user/<path>/acceleratingai-aims25
jupyter notebook --port=8080 --ip=0.0.0.0 --no-browser
```

* Copy the url into your broswer and do your work via a notebook. 

* Alternatively, you can work in standard python importing the libraries as necessary.

Enjoy!
