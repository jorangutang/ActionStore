# Github actions!!!
This repo contains some of the many GitHub actions I have worked on. You can add multiple in-repo shared actions, and public actions.

### 1. Build an application 
### 2. Publish the image (if you like)
### 3. Deploy that image from a tag!

## NOTE:
1. The runners will likely need to be changed to: 
```bash
'runs-on: ubuntu-latest'
```
2. If you want to schedule an action, like a test to run once a year, use cron:
```bash
  on:
    schedule:
      - cron: '0 0 1 1 *'
```
4. you can store files in your shared actions folders, such as python scripts, Dockerfiles, textiles, JSON etc
  This is super useful for storing property files
    eg.
  ```bash
   runs:
    using: 'docker'
    image: 'Dockerfile'
  ```
  and in the dockerfile you could have something like this:
  ```bash
   FROM python:3.8.3-alpine
   COPY . /
   RUN pip install -r requirements.txt
   ENTRYPOINT [ "python" ]
   CMD [ "/main.py" ]
  ```
  that runs a python script which runs a server, you could have a timeout at the end or just kill it.


Check out this resource to see more about its capabilities and fun: https://octopus.com/blog/githubactions-ten-favorite-
