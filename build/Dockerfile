FROM ubuntu:rolling

WORKDIR /usr/src/steamcmd
ENV locale=ja_JP.UTF-8
RUN set -x \
 && apt-get update \
 && apt-get install -y locales \
      lib32gcc1\
      curl \
      tar \
 && rm -rf /var/lib/apt/lists/* \
 && localedef -i ja_JP -c -f UTF-8 -A /usr/share/locale/locale.alias ja_JP.UTF-8 \
 && curl -sqL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf - \
 && ./steamcmd.sh + login anonymous +quit 

ENTRYPOINT [ "/usr/src/steamcmd/steamcmd.sh" ]