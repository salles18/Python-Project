# Python-Project
projeto  em Python que utiliza a biblioteca BeautifulSoup para fazer raspagem de dados de uma página web. Ele baixa os títulos das notícias mais recentes do site de notícias "G1" e exibe na tela:
import requests
from bs4 import BeautifulSoup

url = "https://g1.globo.com/"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

news_list = soup.find_all("a", class_="feed-post-link")
for news in news_list:
    print(news.text)
