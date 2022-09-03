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

- todo app aktifleştirdik
- varsa migrate işlemlerimizi yaptık
- Genel dizinde Procfile dosyası oluşturduk
- pip install gunicorn yaptık
- pip freeze > requirements.txt ile req'e ekledik
- settings'e  STATIC_ROOT = BASE_DIR / "staticfiles"  ekledik
- pip install whitenoise yaptık
- pip freeze > requirements.txt ile req'e ekledik
- settings'te middleware'e 'whitenoise.middleware.WhiteNoiseMiddleware',  ekledik
- pip install django-heroku yaptık
- pip freeze > requirements.txt ile req'e ekledik
- settingse şu kodu eklemeyi unutmayalım STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'
- Settings'e import django_heroku ekledik
- Settingsin altına django_heroku.settings(locals()) ekledik 
- githuba commitledik

#### Heroku tarafı Deploy Aşamaları

- Herokuda sağ üstten Create-new app diyip app ismi verdik
- Settingse geldik reveal config vars' a secret key ekledik
- Buildpackten python seçiyoruz
- Deploy kısmından githubu bağlayıp repo ismi giriyoruz connect diyoruz
- Connectten sonra deploy branch dedik
- sağ üstten more>run console diyip python manage.py migrate yazıyoruz

#### Deploy hatası alanlar için çözüm olabilecek şeyler

- Secret keyinizde # işaretini düzeltiniz
- import django heroku kodunu settingse eklerken altı çiziliyse projenizi ayrı olarak vscode'da açınız, procfile proje yolunuzu göremiyor demektir
- formda importta share kodunu görüyor olabilir onu siliniz
- githuba committen sonra sync yapmayı unutmayınız
- herokuda disconnect edip tekrar bağlanınız ve deploy etmeden once run console'dan python manage.py migrate etmeyi unutmayınız 