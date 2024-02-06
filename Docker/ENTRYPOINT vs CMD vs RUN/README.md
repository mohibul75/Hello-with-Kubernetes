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
