from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from pynput.mouse import Button, Controller
import time
import random


class InstagramBot:
    def __init__(self, username, password):
        self.username = username
        self.password = password
        self.driver = webdriver.Firefox(
            executable_path=r"C:\BotInstagram\bot_curtidas_instagram-master\geckodriver.exe"
        )  # Coloque o caminho para o seu geckodriver aqui

    def login(self):
        driver = self.driver
        driver.get("https://www.instagram.com")
        time.sleep(3)
        try:
            login_button = driver.find_element_by_xpath(
                "//a[@href='/accounts/login/?source=auth_switcher']"
            )
            login_button.click()
        except:
            print('Já estamos na página inicial do Instagram!')
            pass
        user_element = driver.find_element_by_xpath(
            "//input[@name='username']")
        user_element.clear()
        time.sleep(random.randint(4, 6))
        user_element.send_keys(self.username)
        time.sleep(random.randint(4, 6))
        password_element = driver.find_element_by_xpath(
            "//input[@name='password']")
        password_element.clear()
        password_element.send_keys(self.password)
        time.sleep(random.randint(4, 6))
        password_element.send_keys(Keys.RETURN)
        time.sleep(random.randint(4, 6))
        self.seguir(
            "Seguir"
        )

    @staticmethod
    def type_like_a_person(sentence, single_input_field):
        """ Este código irá basicamente permitir que você simule a digitação como uma pessoa """
        print("going to start typing message into message share text area")
        for letter in sentence:
            single_input_field.send_keys(letter)
            time.sleep(random.randint(1, 5) / 30)

    def seguir(self, perfil):
        driver = self.driver
        driver.get("https://www.instagram.com/6segue")
        time.sleep(5)

        hrefs = driver.find_elements_by_tag_name("a")
        follow_hrefs = [elem.get_attribute("href") for elem in hrefs]
        testes = [
            href
            for href in follow_hrefs
            if perfil in href and href.index("/6segue/following/") != -1
        ]

        for follow_href in follow_hrefs:
            try:
                mouse = Controller()
                mouse.position = (783, 230)
                mouse.click(Button.left)
                # Caso o mouse position não ser o mesmo, inserir sua coordenada para Following do Perfil

            except ValueError as err:
                print("pulando link inválido")
                continue

        Perfis= 1
        while (Perfis <= 117):
            try:
                driver.find_element_by_xpath(
                    '//button[@class="sqdOP  L3NKy   y3zKF     "]').click()
                time.sleep(random.randint(2, 8))
            except Exception as e:
                print(e)
                time.sleep(5)
            print('Já seguimos %d ' % Perfis + 'perfis aqui no insta!')
            Perfis += 1
        print('Finalizamos hoje! Aproveite seus seguidores, e volte a me usar no mínimo daqui 24 horas! =)')


easyFollow = InstagramBot(
    "usuário", "senha"
)  # Insira seu usuário e senha
easyFollow.login()
