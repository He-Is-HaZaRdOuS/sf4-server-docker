FROM alpine:3.19

WORKDIR /minecraft

RUN apk update \
    && apk upgrade \
    && apk add ca-certificates \
    && update-ca-certificates \
    && apk add --update coreutils && rm -rf /var/cache/apk/*   \
    && apk add --update openjdk8-jre curl bash coreutils nano unzip \
    && apk add --no-cache nss \
    && rm -rf /var/cache/apk/*

RUN wget -O sf4.zip https://mediafilez.forgecdn.net/files/3565/687/SkyFactory-4_Server_4_2_4.zip

RUN unzip sf4.zip -d ./

RUN chmod +x Install.sh && chmod +x ServerStart.sh

RUN echo "eula=true" > eula.txt

RUN ./Install.sh

EXPOSE 25565

ENTRYPOINT [ ]

