FROM mcr.microsoft.com/devcontainers/base:ubuntu

# 必要なツールをインストール
RUN apt-get update && apt-get install -y \
    curl \
    zip \
    unzip \
    openjdk-17-jdk \
    && rm -rf /var/lib/apt/lists/*

# SDKMAN のインストールと初期化
RUN curl -s "https://get.sdkman.io" | bash \
    && bash -c "source $HOME/.sdkman/bin/sdkman-init.sh && sdk install kotlin && sdk install gradle"

# 環境変数を設定
ENV PATH="/root/.sdkman/candidates/kotlin/current/bin:/root/.sdkman/candidates/gradle/current/bin:$PATH"

# 動作確認
RUN bash -c "source $HOME/.sdkman/bin/sdkman-init.sh && kotlin -version && gradle --version"
