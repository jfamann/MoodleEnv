# MoodleEnv

__- Arborescence du projet__

    - build
        - mysql
            - Dockerfile
            - my.cnf
        - php
            - Dockerfile.74
            - Dockerfile.80
            - 000-default-74.conf
            - 000-default-80.conf
    - dbData (persistance des données MySQL)
    - moodle_3.8
        - src (code Moodle 3.8)
        - data
    - moodle_4.0
        - src (code Moodle 4.0)
        - data
    docker-compose

----------------

__- Import du code source Moodle (https://github.com/moodle/moodle.git)__
    1/ Importer le code source Moodle 3.8 (branche 3.8) dans moodle_3.8\src
    2/ Importer le code source Moodle 4.0 (branche 3.8) dans moodle_4.0\src

----------------

__- Initialiser la DB MySQL__
    1/Créer un user moodle -> mdp: moodle

    2/Créer une Database : moodle_3.8
    3/Donner les droits au user moodle (ALL PRIVILEGES) sur la DB moodle_3.8

    4/Créer une Database : moodle_4.0
    5/Donner les droits au user moodle (ALL PRIVILEGES) sur la DB moodle_4.0

----------------

__- Construction d'une plateforme de DEV pour Moodle__

    PHP-apache 7.4 pour Moodle 3.8
        Dockerfile -> build\php\DockerFile.74
    PHP-apache 8.0 pour Moodle 4.0
        Dockerfile -> build\php\DockerFile.80
    PHPMyadmin
    MySQL
        Dockerfile -> build\mysql\DockerFile
        + my.cnf
        MySQL va utiliser le répertoire /dbData pour persister ses données
    Mailhog (SMTP server)

----------------

__- Utiliser le docker-compose à la racine du projet pour contruire les images + containers__
    -> docker compose up


