---
id: p2mfNaM5RmjyPu2NxPk2X
title: Docker File
desc: ''
updated: 1641933853388
created: 1641931387867
---

## Tips

consider each line of the docker a layer of the abstraction this comes into play in the next example.

## Base example of having to install all your dependencies and everything

Negates the utility of docker if the image is not just "good to go" but here's how to do this

---

```docker
FROM python:3.9.7

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
```

---

- `FROM python:3.9.7`
  - Specify what python version to run in the base image
  - "python" is the image
  - "3.9.7" is the version of that image
- `WORKDIR /usr/src/app`
  - "/usr/src" is a valid path in the image
  - "/app" is the path we want to tack on and create for our app code
- `COPY requirements.txt ./`
  - Grab the requirements file into the image
- `RUN pip install --no-cache-dir -r requirements.txt`
  - Install dependencies
- `COPY . .`
  - "." first dot is current directory, second "." is `WORKDIR`
  - Move our source code into the image
  - This is where layering comes into play, when you change source code files
    - The only thing that changed was source code so this step and below is what gets re-ran
  - Each layers results are cached, so when you change something it only re-runs steps where something has changed compared to the cached image layers.
    - Only changed source code? then only re-run the step where we copy over source code files
- `CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]`
  - The array of commands to run once the image is spun up
  - each array items is either a switch or a param
  - essentially any time you have a space between anything in the command that is when you make a separate item in the array for it.

At this point you can now create the image using [[s.containers.docker.cmd.build]]