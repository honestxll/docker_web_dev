FROM bitnami/php-fpm
MAINTAINER honest <honestxll@gmail.com>

COPY ./config/sources.list /etc/apt

RUN apt-get update && apt-get install -y vim git curl \
&& composer config -g repo.packagist composer https://packagist.laravel-china.org \
&& echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.bashrc

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash \
&& echo 'export NVM_NODEJS_ORG_MIRROR=https://npm.taobao.org/mirrors/node/' >> ~/.bashrc \
&&. ~/.bashrc \
&& nvm install --lts \
&& npm --registry https://registry.npm.taobao.org i -g nrm \
&& nrm use taobao \
&& npm config set user 0 \
&& npm config set unsafe-perm true \
&& npm i -g yarn \
&& npm i -g @vue/cli \
&& npm i -g @adonisjs/cli \
&& npm i -g @nestjs/cli

WORKDIR /mnt/app