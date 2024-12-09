FROM haskell:9-slim
USER 0
RUN mkdir /app
WORKDIR /app
SHELL ["/bin/bash", "-c"]

RUN cabal update
RUN cabal install cabal-install
RUN cabal install scotty 

#DEV
RUN apt update 
RUN apt install git libicu-dev libncurses-dev libgmp-dev zlib1g-dev -y 
RUN cabal install haskell-language-server haskell-debug-adapter 
RUN cabal install ghci-dap

RUN apt install curl -y
RUN curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz
RUN tar -C /opt -xzf nvim-linux64.tar.gz
RUN rm nvim-linux64.tar.gz
RUN ln -sr /opt/nvim-linux64/bin/nvim /bin/nvim
RUN git clone https://github.com/LapTapk/nvim /root/.config/nvim 
#VED

#COPY . .

#DEV
CMD bash
#VED
