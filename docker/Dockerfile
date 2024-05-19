FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update -y
RUN apt install build-essential curl libc++-dev -y

ENV PATH="/root/.cargo/bin:${PATH}"
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y && \
	. $HOME/.cargo/env

RUN rustup default nightly
RUN rustup update

RUN cargo +nightly install hvm
RUN cargo +nightly install bend-lang

RUN apt clean