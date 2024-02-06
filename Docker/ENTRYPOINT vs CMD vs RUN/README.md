## Docker File Instruction Formats
In a Dockerfile, instructions can be written in two formats: the exec form and the shell form. The choice between these two formats applies to the RUN, CMD, and ENTRYPOINT instructions. Below are examples illustrating both formats:

### Shell Format
In a Dockerfile, instructions can be written in two formats: the exec form and the shell form. The choice between these two formats applies to the RUN, CMD, and ENTRYPOINT instructions. Below are examples illustrating both formats:
- CMD ls -la
- ENTRYPOINT ls -la
- RUN apt-get update

### exec format
In the exec form, instructions are written as a JSON array. Each element in the array represents a separate word in the command. The following examples showcase the exec form:
- CMD ["ls", "-la"]
- ENTRYPOINT ["ls", "-la"]
- RUN ["apt-get", "update"]
