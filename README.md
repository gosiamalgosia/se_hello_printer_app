# Simple Flask App

Aplikacja Dydaktyczna wyświetlająca imię i wiadomość w różnych formatach dla zajęć
o Continuous Integration, Continuous Delivery i Continuous Deployment.

- W projekcie wykorzystamy virtual environment, dla utworzenia hermetycznego środowisko dla aplikacji:

  ```
  # tworzymy hermetyczne środowisko dla bibliotek aplikacji:
  $ python3 -m venv .venv

  # aktywowanie hermetycznego środowiska
  $ source .venv/bin/activate

  make deps
  # lub
  $ pip install -r requirements.txt
  $ pip install -r test_requirements.txt

  # zobacz
  $ pip list
  ```

  Sprawdź: [tutorial venv](https://docs.python.org/3/tutorial/venv.html) oraz [biblioteki flask](http://flask.pocoo.org).

- Uruchamianie applikacji:

  ```
  # jako zwykły program
  $ python main.py

  make run
  # albo:
  $ PYTHONPATH=. FLASK_APP=hello_world flask run
  ```

- Uruchamianie testów (see: http://doc.pytest.org/en/latest/capture.html):

  ```
  make test
  # lub
  $ PYTHONPATH=. py.test
  $ PYTHONPATH=. py.test --verbose -s
  ```

- Kontynuując pracę z projektem, aktywowanie hermetycznego środowiska dla aplikacji py:

  ```
  # deaktywacja
  $ deactivate
  ```

  ```
  ...

  # aktywacja
  $ source .venv/bin/activate
  ```


### Status TravisCI:
[![Build Status](https://travis-ci.com/gosiamalgosia/se_hello_printer_app.svg?branch=master)](https://travis-ci.com/gosiamalgosia/se_hello_printer_app)

  ```
  # uruchamiamy terminal z SUDO !!!
  $ make docker_run

  # czy app działa poprawnie
  $ curl 127.0.0.1:5000

  #czy docker uruchomiony:
  $ docker ps -a    

  # logi:
  $ docker logs hello-world-printer-dev

  # nie restartujemy, zatrzymujemy, kasujemy i uruchamiamy na nowo !!
  $ docker stop hello-world-printer-dev
  $ docker start hello-world-printer-dev
  $ docker rm hello-world-printer-dev
  $ make docker_run


  ```

# Pomocnicze

## Ubuntu

- Instalacja dockera: [dockerce howto](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

## Centos

- Instalacja docker-a:

  ```
  $ yum remove docker \
        docker-common \
        container-selinux \
        docker-selinux \
        docker-engine

  $ yum install -y yum-utils

  $ yum-config-manager \
      --add-repo \
      https://download.docker.com/linux/centos/docker-ce.repo

  $ yum makecache fast
  $ yum install -y docker-ce
  $ systemctl start docker
  ```
## Monitoring w statuscake.com
https://app.statuscake.com/UptimeStatus.php?tid=6003177

### Monitoring StatusCake:
![Build Status](https://app.statuscake.com/button/index.php?Track=6003177&Days=1&Design=1)
