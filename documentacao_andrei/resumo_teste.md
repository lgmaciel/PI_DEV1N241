## Resumo do Projeto — Jogo de Perguntas com Notícias via RSS

O projeto consiste na criação de um jogo interativo de perguntas e respostas baseado em notícias obtidas por meio de feeds RSS. As notícias são coletadas automaticamente, processadas e utilizadas para gerar perguntas de múltipla escolha, divididas por níveis de dificuldade: fácil, médio e difícil.

As principais funcionalidades incluem:

Leitura de feeds RSS utilizando a biblioteca feedparser;

Extração e limpeza do conteúdo das notícias com BeautifulSoup;

Geração automática de perguntas baseadas nos títulos e conteúdos das notícias;

Classificação das perguntas por dificuldade;

Interface gráfica desenvolvida com tkinter para interação com o jogador;

Sistema de pontuação e controle de progresso;

Armazenamento de dados (notícias, perguntas, pontuação etc.) em banco de dados SQLite.

O jogo é construído em Python, utilizando bibliotecas como feedparser, beautifulsoup4, tkinter e sqlite3.