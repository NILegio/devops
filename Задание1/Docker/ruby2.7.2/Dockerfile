FROM ubuntu:20.04

ENV TZ=Europe/Minsk
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update -y 
RUN apt-get install -y curl git make gcc build-essential 
RUN apt-get install -y zlib1g-dev libssl-dev libreadline-dev libyaml-dev libxml2-dev libxslt-dev

		
RUN git clone https://github.com/rbenv/rbenv.git /root/.rbenv

RUN git clone https://github.com/rbenv/ruby-build.git /root/.rbenv/plugins/ruby-build

RUN /root/.rbenv/plugins/ruby-build/install.sh

ENV PATH /root/.rbenv/bin:$PATH
ENV PATH /root/.rbenv/shims:$PATH

RUN echo 'eval "$(rbenv init -)"' >> /etc/profile.d/rbenv.sh 
RUN echo 'eval "$(rbenv init -)"' >> .bashrc

RUN rbenv install 2.7.2
RUN rbenv global 2.7.2
