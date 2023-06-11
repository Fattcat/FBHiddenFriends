from getpass import getpass
from facebook_scraper import FacebookScraper

# Získať meno a heslo používateľa
username = input("Zadajte vaše používateľské meno na Facebooku: ")
password = getpass("Zadajte vaše heslo: ")

# Získať meno používateľa, od ktorého chceme zistiť skrytých priateľov
target_username = input("Zadajte používateľské meno, od ktorého chcete získať skrytých priateľov: ")

# Inicializácia FacebookScraperu
scraper = FacebookScraper()
scraper.set_user(username, password)

# Získať zoznam priateľov danej osoby
friends = scraper.get_friends(target_username)

# Získať zoznam priateľov, ktorí majú daného používateľa pridaného ako priateľa
mutual_friends = [friend for friend in friends if target_username in scraper.get_friends(friend)]

# Zapísať zoznam skrytých priateľov do súboru
with open("FB-Friends.txt", "a") as file:
    file.write(target_username + "\n")
    file.write(", ".join(mutual_friends) + "\n\n")

print(f"Zoznam skrytých priateľov od používateľa {target_username} bol uložený do súboru 'FB-Friends.txt'.")

# Vypísať počet priateľov
print(f"Celkový počet priateľov: {len(mutual_friends)}")
