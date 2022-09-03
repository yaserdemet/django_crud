<!-- Please update value in the {}  -->

<h1 align="center">ToDo App</h1>


<div align="center">
  <h3>
    <a href="https://{your-demo-link.your-domain}">
      Demo
    </a>
     | 
    <a href="https://{your-url-to-the-solution}">
      Project
    </a>
 
  </h3>
</div>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Overview](#overview)
  - [Built With](#built-with)
- [How To Use](#how-to-use)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)

<!-- OVERVIEW -->

## Overview

![screenshot](todo.PNG)

### Built With

<!-- This section should list any major frameworks that you built your project using. Here are a few examples.-->

- HTML
- CSS
- JS
- Django

## How To Use

<!-- This is an example, please update according to your application -->

To clone and run this application, you'll need [Git](https://git-scm.com) 
```bash
# Clone this repository
$ git clone https://github.com/your-user-name/your-project-name

# Install dependencies
    $ python -m venv env
    > env/Scripts/activate (for win OS)
    $ source env/bin/activate (for macOs/linux OS)
    $ pip install -r requirements.txt
# Edit .backend.env to .env
# Add SECRET_KEY in .env file

# Run the app
    $ python manage.py runserver
```

## Acknowledgements
- Information for your projects

## Contact

- Website [your-website.com](https://{your-web-site-link})
- GitHub [@your-username](https://{github.com/your-usermame})

- Linkedin [@your-linkedin](https://{linkedin.com/your-username})
- Twitter [@your-twitter](https://{twitter.com/your-username})


#### Deploya başlangıç-vscode aşamaları

1- todo app aktifleştirdik
2- varsa migrate işlemlerimizi yaptık
3- Genel dizinde Procfile dosyası oluşturduk
4- pip install gunicorn yaptık
5- pip freeze > requirements.txt ile req'e ekledik
6- settings'e  STATIC_ROOT = BASE_DIR / "staticfiles"  ekledik
7- pip install whitenoise yaptık
8- pip freeze > requirements.txt ile req'e ekledik
9- settings'te middleware'e 'whitenoise.middleware.WhiteNoiseMiddleware',  ekledik
10- pip install django-heroku yaptık
11- pip freeze > requirements.txt ile req'e ekledik
12- settingse şu kodu eklemeyi unutmayalım STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'
13- Settings'e import django_heroku ekledik
14- Settingsin altına django_heroku.settings(locals()) ekledik 
15- githuba commitledik

#### Heroku tarafı Deploy Aşamaları

1- Herokuda sağ üstten Create-new app diyip app ismi verdik
2- Settingse geldik reveal config vars' a secret key ekledik
3- Buildpackten python seçiyoruz
4- Deploy kısmından githubu bağlayıp repo ismi giriyoruz connect diyoruz
5- Connectten sonra deploy branch dedik
6- sağ üstten more>run console diyip python manage.py migrate yazıyoruz

#### Deploy hatası alanlar için çözüm olabilecek şeyler

1-Secret keyinizde # işaretini düzeltiniz
2-import django heroku kodunu settingse eklerken altı çiziliyse projenizi ayrı olarak vscode'da açınız, procfile proje yolunuzu göremiyor demektir
3-formda importta share kodunu görüyor olabilir onu siliniz
4-githuba committen sonra sync yapmayı unutmayınız
5-herokuda disconnect edip tekrar bağlanınız ve deploy etmeden once run console'dan python manage.py migrate etmeyi unutmayınız 