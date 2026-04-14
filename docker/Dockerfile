FROM cruizba/ubuntu-dind:latest

RUN apt-get update && apt-get install -y --no-install-recommends \
	sudo \
	curl \
	git

COPY scripts/install-github-cli.sh .
RUN ./install-github-cli.sh

WORKDIR /app

RUN curl -fsSL https://get.docker.com | bash
RUN curl -fsSL https://claude.ai/install.sh | bash
RUN echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
RUN git clone https://github.com/jargon64/nanoclaw.git

WORKDIR /app/nanoclaw

CMD ["tail", "-f", "/dev/null"]
