# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Create an ec2
Git clone repo you are working with
Follow the README
Whenever you run a server make sure it doesnt just run on the local host i.e→://127.0.0.1:8000/
Instead mention it like →  python3 manage.py runserver 0.0.0.0:8000
Make sure the you edit the inbound rules according to the port and that it allows traffic to that port
Add your ip to allowed hosts or just add ‘*’ in allowed hosts
Make a Dockerfile and add all the requirements needed
```$sudo docker build . -p 8000:8000``` (build a Docker image)
```$sudo docker run -p 8000:8000 <docker-image>``` (run the docker image and mask the port to the IP of host)



JENKINS:-
Install Java → ```bash 
$sudo apt install openjdk-11-jre```

Then just copy paste this command for jenkins 

```bash
  $sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null ```

```$sudo apt-get update```


```bash $sudo apt-get install jenkins```

Then ```
bash $sudo systemctl enable jenkins ```

```bash $sudo systemctl start jenkins```
```$sudo systemctl status jenkins ```

Then add inbound rules to accept traffic from port 8080 (jenkins runs on port 8080)

Now setup an agent in jenkins (performs all the steps for the pipeline)
Create a node (the environment where the pipeline will run)
If you want the node to run all the shell scripts, run commands basically everything needed for the pipeline you Create a permanent node
Setup your node as required 
Now Create a job (job is a pipeline where all the steps will be mentioned and they are executed automatically therefore automating the process)
THE JOB → THE WHOLE POINT OF JENKINS LIES HERE
```$Chmod 777 django-todo```
(giving permission to all the users so that jenkins agent also has permission to access the files)
Steps to write the shell script
cd /home/ubuntu/projects/Django-ToDo-CICD (go into the directory where everything is including the Dockerfile)
```$sudo docker build . -t todo-dev```
```$sudo docker run -d -p 8000:8000 todo-dev```
(if anything happens you can always go to configure the job and fix your shell script)

