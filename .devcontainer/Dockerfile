FROM qmcgaw/latexdevcontainer:latest-full
FROM manimcommunity/manim:latest

RUN apt-get update && apt-get install -y fish
RUN apt update -y && apt install fontconfig python3 -y

RUN apt-get update \
    && apt-get install --no-install-recommends -y \
    xdg-utils \
    vlc
