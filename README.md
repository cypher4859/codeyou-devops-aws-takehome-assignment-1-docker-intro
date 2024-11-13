# Docker Intro - Take Home Assignment

### Due Date: One week from today

#### Objective:
The purpose of this assignment is to reinforce your understanding of Docker and practice the commands you learned in class. By the end of this homework, you should feel more comfortable with creating, running, managing, and investigating Docker containers.

### Tasks:

1. **Pulling Docker Images**
    - Pull the latest version of the following Docker images: `nginx`, `alpine`, and `ubuntu`.
    - Verify that the images have been downloaded successfully by listing all images on your system.
    - **Command Reference**: Use `docker image pull` and `docker image ls`.

2. **Running Containers**
    - Create and start a container for each of the images (`nginx`, `alpine`, and `ubuntu`).
    - For `nginx`, run it in detached mode so it continues running in the background.
    - For `alpine` and `ubuntu`, start them interactively, and use `/bin/sh` to get a shell inside the container.
    - **Command Reference**: Use `docker container run -d` for `nginx` and `docker container run -it` for `alpine` and `ubuntu`.

3. **Investigate Running Containers**
    - List all the running containers on your system.
    - Use `docker exec` to execute the `ps aux` command inside the `nginx` container to see which processes are running.
    - Identify the Process ID (PID) and User ID (UID) of the main `nginx` process.
    - **Command Reference**: Use `docker container ls`, `docker exec`, and `ps aux`.

4. **Resource Monitoring**
    - Use Docker to monitor the resource usage of your `nginx` container. Specifically, observe the CPU, memory, and network usage for a few seconds.
    - **BONUS**: How can you run the command to monitor resources without blocking the terminal? Document your findings.
    - **Command Reference**: Use `docker stats`.

5. **Stopping and Removing Containers**
    - Stop the `nginx` container that you started earlier.
    - Remove the `nginx` container from your system.
    - Verify that there are no `nginx` containers left using the list command.
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

