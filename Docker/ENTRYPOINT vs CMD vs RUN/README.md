## Docker File Instruction Formats
In a Dockerfile, instructions can be written in two formats: the exec form and the shell form. The choice between these two formats applies to the RUN, CMD, and ENTRYPOINT instructions. Below are examples illustrating both formats:

### Shell Format
In the shell form, instructions are written as a simple string, similar to how commands would be entered directly in a terminal. The following examples demonstrate the shell form:
- CMD ls -la
- ENTRYPOINT ls -la
- RUN apt-get update

When using the shell form, commands are run under the control of "/bin/sh -c" in the container. This means that the specified command is executed within a shell, allowing for shell processing such as variable substitution and other shell features.

### exec format
In the exec form, instructions are written as a JSON array. Each element in the array represents a separate word in the command. The following examples showcase the exec form:
- CMD ["ls", "-la"]
- ENTRYPOINT ["ls", "-la"]
- RUN ["apt-get", "update"]

the exec form runs commands directly without the need for an intermediate shell. The executable is called directly, bypassing shell processing.

## CMD
The CMD instruction in a Dockerfile defines the default command that should be executed when a Docker container starts. It serves as the primary executable for the container. However, if a user specifies a different command while running the container, that user-provided command takes precedence over the CMD instruction.
```sh
FROM ubuntu:20.04
CMD ["pwd"]
```
In this case, if you start the container without providing a specific command, it will execute the default command pwd, which prints the present working directory.

However, if you run the container with a different command, such as:
```sh
docker run <image-name> ls
```
The user-provided command (ls in this example) takes precedence over the default CMD, and the container will list the files and directories in the root directory instead.

Use Cases of CMD:
## Exec Mode:
```sh
CMD ["ls", "-al"]
```
In this example, the CMD is written in exec mode, directly specifying the command and its arguments. When the container starts, it executes the ls -al command.
## Passing Arguments to ENTRYPOINT:
```sh
CMD ["parameter1", "parameter2"]
```
This form of CMD is used to pass arguments to the ENTRYPOINT instruction if it is defined in the Dockerfile.

## Shell Format:
```sh
CMD ls -la
```
In this shell format, the CMD instruction runs under /bin/sh -c ls -la. It provides flexibility with shell features such as variable substitution.

## Multiple CMD Instructions:
If a Dockerfile contains multiple CMD instructions, only the last one will be executed. Each CMD instruction overwrites the previous one.
Understanding the nuances of the CMD instruction is essential for configuring the default behavior of Docker containers and handling user-provided commands effectively.
