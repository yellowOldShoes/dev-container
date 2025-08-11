# 使用微软官方的Python开发基础镜像
ARG VARIANT="3.10"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# 将项目根目录的 requirements.txt 复制到临时目录
# 这样 postCreateCommand 就能找到它
COPY requirements.txt /tmp/pip-tmp/
# 在容器构建时就预先安装好依赖，可以加快后续启动速度
RUN pip install --user -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmp