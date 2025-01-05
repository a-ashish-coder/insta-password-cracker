import requests
from bs4 import BeautifulSoup

def instagram_password_heist(username):
    url = f"https://www.instagram.com/{username}/"
    response = requests.get(url)
    
    if response.status_code == 200:
        soup = BeautifulSoup(response.text, 'html.parser')
        # Extracting the password (hypothetical scenario)
        password = soup.find('input', {'name': 'password'})['value']
        return password
    else:
        return "User not found."

username = input("Enter the Instagram username: ")
print(instagram_password_heist(username))
