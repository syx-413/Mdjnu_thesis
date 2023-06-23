# FROM qmcgaw/latexdevcontainer:latest-full
# FROM manimcommunity/manim:latest

# RUN apt-get update && apt-get install -y fish
# RUN apt update -y && apt install fontconfig python3 -y

# RUN apt-get update \
#     && apt-get install --no-install-recommends -y \
#     xdg-utils \
#     vlc

# 第一阶段：构建 LaTeX 环境
FROM qmcgaw/latexdevcontainer:latest-full AS latex-build
RUN apt-get update && apt-get install -y fish \
    && apt update -y && apt install fontconfig python3 -y

# 第二阶段：构建 Manim 环境
FROM manimcommunity/manim:latest AS manim-build
RUN apt-get update && apt-get install -y fish \
    && apt-get install --no-install-recommends -y xdg-utils vlc

# 第三阶段：合并两个镜像
FROM final-base-image
# 复制 LaTeX 环境的文件和依赖项
COPY --from=latex-build /path/to/files /app
# 复制 Manim 环境的文件和依赖项
COPY --from=manim-build /path/to/files /app
# 添加其他步骤...
