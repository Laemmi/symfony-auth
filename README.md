# Symfony auth

## Description
Symfony app with simple authenticator and user CRUD

## Init new app

    symfony new symfony-auth \
    && cd symfony-auth \
    && sudo rm -r .git/ \
    && git init \
    && composer require --dev symfony/maker-bundle symfony/profiler-pack \
    && composer require annotations security symfony/orm-pack twig form validator \
    && echo 'DATABASE_URL=sqlite:///%kernel.project_dir%/var/data.db' >> .env.dev.local \
    && bin/console doctrine:database:create \
    && bin/console make:user \
    && bin/console make:migration \
    && bin/console doctrine:migrations:migrate \
    && bin/console make:registration-form \
    && bin/console make:auth \
    && bin/console make:crud 