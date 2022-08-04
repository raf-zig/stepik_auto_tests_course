from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import Select
import time 

try:
    link = "http://suninjuly.github.io/selects2.html"
    browser = webdriver.Chrome()
    browser.get(link)

    x_element = browser.find_element(By.ID, "num1")
    x = x_element.text
   
    y_element = browser.find_element(By.ID, "num2")
    y = y_element.text

    z = str(int(x) + int(y))

    select = Select(browser.find_element(By.TAG_NAME, "select"))
    select.select_by_value(z)

    
    button_2 = browser.find_element(By.CLASS_NAME, "btn")
    button_2.click()

    time.sleep(1)

finally:
    time.sleep(10)
    browser.quit()
    
