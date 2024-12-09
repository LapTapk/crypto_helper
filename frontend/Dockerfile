FROM python:3.12-slim
USER 0
RUN mkdir /app
WORKDIR /app
SHELL ["/bin/bash", "-c"]

COPY requirements.txt .
RUN pip install -r requirements.txt

#DEV
RUN pip install pyright 
RUN apt update 
RUN apt install git -y 

RUN apt install curl -y
RUN curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz
RUN tar -C /opt -xzf nvim-linux64.tar.gz
RUN rm nvim-linux64.tar.gz
RUN ln -sr /opt/nvim-linux64/bin/nvim /bin/nvim
RUN git clone https://github.com/LapTapk/nvim.git /root/.config/nvim
#VED

#COPY . .

#DEV
CMD bash
#VED
