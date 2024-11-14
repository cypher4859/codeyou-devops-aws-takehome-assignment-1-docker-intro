# Docker Intro - Take Home Assignment
### Due Date: One week from today

#### Objective:
The purpose of this assignment is to reinforce your understanding of Docker and practice the commands you learned in class. By the end of this homework, you should feel more comfortable with creating, running, managing, and investigating Docker containers.

### Tasks:

1. **Pulling Docker Images**
    - Pull the latest version of the following Docker images: `redis`, `alpine`, and `ubuntu`.
        - Verify that the images have been downloaded successfully by listing all images on your system.
        - **Command Reference**: Use `docker image pull` and `docker image ls`.

2. **Running Containers**
    - Create and start a container for each of the images (`redis`, `alpine`, and `ubuntu`).
      - For `redis`, run it in detached mode so it continues running in the background for later investigation.
          - *NOTE*: This container when run will execute the redis service which will run until stopped. That's why we want to run it in the background, i.e. in detached mode.
          - **Command Reference**: Use `docker container run -d <IMAGE>` to run in detached mode. 
      - For `alpine`, start it interactively and use `/bin/sh` to get a shell inside the container.
          - Once inside the Alpine container, run `ls` to list all files at the root (`/`) directory.
          - **Command Reference**: Remember from the Challenge that we use `docker container run -it <IMAGE> <COMMAND>` to run a container and hook up to it interactively (`-it`) to execute a certain <COMMAND>.
      - For `ubuntu`, start it interactively and use `/bin/sh` to get a shell inside the container.
        - Once inside the Ubuntu container, run `ls` to list all the files at `/etc` directory.
        - **Command Reference**: Use `docker container run -it alpine /bin/sh` or `docker container run -it ubuntu /bin/sh` for `alpine` and `ubuntu`. The `-t` means to allocate a terminal in the container. Most of the time these two option flags are used together as `-it`.

3. **Investigate Running Containers**
    - *NOTE*: For the`redis` container, ensure that the container is started and install useful packages like `lsof`, `procps` (for `ps`), and optionally `net-tools` (for networking commands, like ifconfig). This will provide a more realistic service environment to investigate.
        - You can install these packages by `apt update && apt install -y lsof procps` from the terminal in the container or by using `docker exec`. These packages aren't typically in the redis image because it's meant to be lightweight but they are default standard tools on most linux systems.
        - **Command Reference**: Use `docker container run -d` for `redis` and `docker container run -it` for `alpine` and `ubuntu`.
    - List all the running containers on your system.
    - Use `docker exec` to execute the `ps aux` command inside the `redis` container to see which processes are running, including the Redis server. If you've already setup a terminal within the container using `/bin/sh` or `/bin/bash` then just run `ps aux` from the command line instead. Make note of the `redis-server` process and it's PID.
    - Use `docker exec` to either get a new terminal into the container or to execute the next step against the `redis` container in order to find files are currently open by the Redis process
      - Using the PID for the running Redis service, use `lsof -p <PID>` to find which files are currently open by the Redis process.
    - **Command Reference**: Use `docker container ls`, `docker exec`, `ps aux`, `lsof`. Use `docker exec -it <CONTAINER> /bin/sh` to get a terminal into an already running container or replace `/bin/sh` with the name of a command, e.g. `lsof`, `ps aux`, to execute the command inside the container.

4. **Resource Monitoring**
    - Use Docker to monitor the resource usage of your `redis` container. Specifically, observe the CPU, memory, and network usage for a few seconds. Document your findings.
    - **BONUS**: How can you run the command to monitor resources without blocking the terminal? Document your findings.
    - **Command Reference**: Use `docker stats`.

5. **Stopping and Removing Containers**
    - Stop the `redis` container that you started earlier.
    - Remove the `redis` container from your system.
    - Verify that there are no `redis` containers left using the list command.
    - **Command Reference**: Use `docker container stop`, `docker container rm`, and `docker container ls -a`.

6. **Container Cleanup**
    - Remove all the containers and images you used for this assignment.
    - List the images and containers after removing them to confirm that your system is clean.
    - **Command Reference**: Use `docker container rm`, `docker image rm`, and the `ls` commands.

### Submission Requirements:
- Submit a text file or document containing the commands you used for each task, along with brief explanations of what each command does. Please feel free to use your own words; the goal is for me to understand what you're saying rather than know exactly what Docker does, so use your best judgment.
- Include any output or screenshots if applicable (e.g., the output of `docker stats` or `docker container ls`).

### Tips:
- Refer to the Docker cheatsheet we covered in class for all the necessary commands.
- Don’t be afraid to use `docker --help` to understand available options or get unstuck.
- Practice using `CTRL+c` to stop a running command in the terminal if needed.

---

This assignment is designed to get you comfortable with essential Docker commands and operations. If you encounter any difficulties, make sure to note them down, as we will discuss common issues and solutions in our next session. Good luck!

