### Pipenv Images for linux and wine

---

Thoses images were made to be used with gitlab ci (mainly for pipenv + pyinstaller), but can be used as a regular container too.


### Usage
----
```bash
docker run -dti tuoni/pipenv-wine:python37 /bin/bash
```
Then copy the sources file into the running container.
```bash
docker cp myrepo mycontainer:/
```
Attach the container and build
```bash
docker attach mycontainer
root@7bb22217c96b:~# cd myrepo
root@7bb22217c96b:/myrepo# pipenv update && pipenv run pyinstaller --onefile myfile.py
```
You can retrieve the generated build by running
```bash
docker cp mycontainer:/myrepo/dist/myfile.exe
```

