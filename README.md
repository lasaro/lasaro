from selenium import webdriver
from selenium.webdriver.chrome.service import Service
import pyautogui
from selenium.webdriver.support.ui import Select 
import time

s=Service('/home/lasaro/Downloads/chromedriver_linux64/chromedriver')
navegador = webdriver.Chrome(service=s)

j = 1500000000
g = 13
for i in range(0, j):        
    navegador.get('https://www.google.com.br')
    navegador.find_element("xpath", '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[1]/div/div[2]/input').click()
    navegador.find_element("xpath", '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[1]/div/div[2]/input').send_keys('DEIXEM O NORDESTE VOTAR')
    navegador.find_element("xpath", '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[4]/center/input[1]').click()
    navegador.get('https://www.google.com.br')
    navegador.find_element("xpath", '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[1]/div/div[2]/input').click()
    navegador.find_element("xpath", '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[1]/div/div[2]/input').send_keys('PRF agindo como milícia')
    navegador.find_element("xpath", '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[4]/center/input[1]').click()
    if (i != 0) and (i % g == 0):        
        print("consulta: "  + str(i) + " - multiplo de: "  + str(g))
        navegador.close()
        s=Service('/home/lasaro/Downloads/chromedriver_linux64/chromedriver')
        navegador = webdriver.Chrome(service=s)
    else:
        print("consulta: "  + str(i))
else:
    print("foram feitas: " + str(j) + " pesquisas")
