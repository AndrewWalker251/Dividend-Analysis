# coding: utf-8

# In[14]:
from selenium import webdriver
chrome_path = r"C:\Users\Andrew\chromedriver_win32\chromedriver.exe"
driver = webdriver.Chrome(chrome_path)
driver.get("http://www.dividenddata.co.uk/dividendyield.py?market=ftse100")

# In[15]:

watch_list = ['HSBA','WPP','GSK','ULVR','DGE','LGEN','NG.','BP.']

# In[16]:

from lxml import html
import requests

webpage = ('http://www.hl.co.uk/shares/stock-market-summary/ftse-100')
page = requests.get(webpage)
tree = html.fromstring(page.content)

for stock in watch_list:

    print(tree.xpath('//*[@id="ls-mid-%s-L"]/text()' % stock))

# In[17]:

# Creating classes and objects
class Stock(object):
    name = ""
    dividend_rate = 0
    price = 0

 # The class "constructor" - It's actually an initializer
    def __init__(self, name, dividend_rate, price):
        self.name = name
        self.dividend_rate= dividend_rate
        self.price = price

def make_stock(name, dividend_rate, price):
    stock = Stock(name,dividend_rate, price)
    return stock

def displayStock(self):
      print "Name : ", self.name,  "Dividend Rate :", self.dividend_rate.text, "  Price: ", self.price

# In[21]:

for stock in watch_list:

    price = (tree.xpath('//*[@id="ls-mid-%s-L"]/text()' % stock))[0]
    dividend_rate = (driver.find_element_by_xpath("""//*[@id="%s"]/td[6]""" % stock))
    stock = make_stock(stock,dividend_rate, price)

    displayStock(stock)
