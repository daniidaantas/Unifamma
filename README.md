from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.common.by import By

# Configurações do Selenium para usar o Chrome
chrome_options = Options()
chrome_options.add_argument("--headless")
chrome_options.add_argument("--disable-gpu")
chrome_options.add_argument("--window-size=1280x1696")

# Caminho para o ChromeDriver
chrome_driver_path = "/usr/bin/chromedriver"

# Serviço para o ChromeDriver
service = Service(executable_path=chrome_driver_path)

# Inicializando o WebDriver
driver = webdriver.Chrome(service=service, options=chrome_options)

# Caminho para o arquivo HTML local
file_path = f"file://{project_path}/index.html"

# Carregar a página
driver.get(file_path)

# Fazer captura de tela
screenshot_path = "/mnt/data/landing_page_screenshot.png"
driver.save_screenshot(screenshot_path)

# Fechar o WebDriver
driver.quit()

screenshot_path
