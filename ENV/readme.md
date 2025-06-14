OBUILD Instruction:
It is used to trigger if someone is trying use your image then you can force them to keep some files in their workspace/config otherwise the build will fail.

The ONBUILD instruction in a Dockerfile is used to define trigger instructions that execute only when the image is used as a base for another build. This is useful when creating base images that should automatically apply certain actions when extended.
How ONBUILD Works
- The ONBUILD instruction does not execute when building the base image.
- It executes later when another Dockerfile uses the base image with FROM.
Example Usage
Base Image Dockerfile (base.Dockerfile)
FROM python:3.9

# Define ONBUILD instructions
ONBUILD COPY requirements.txt /app/
ONBUILD RUN pip install -r /app/requirements.txt


Child Image Dockerfile (child.Dockerfile)
FROM my-python-base

COPY . /app
CMD ["python", "app.py"]


Explanation
- The base image (my-python-base) contains ONBUILD instructions.
- When the child image (child.Dockerfile) is built, the ONBUILD instructions automatically execute:
- COPY requirements.txt /app/
- RUN pip install -r /app/requirements.txt
- This ensures that every child image inherits the dependency installation process.
Use Cases
✅ Standardizing builds → Ensures all child images follow the same setup.
✅ Reducing duplication → Avoids repeating common steps in multiple Dockerfiles.
✅ Automating dependency management → Useful for frameworks like Flask or Node.js.