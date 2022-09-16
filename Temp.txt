import random
import webbrowser
from time import sleep

Main_URL = "https://script.google.com/macros/s/AKfycbzbVH970Zc7oNWUHlcxtDn-c4I3lYcCUcNH_hsgV_h6vdxln3DuK0e5BMtEt0ZQwFVx2Q/exec"

with open("RFID Student Data.txt", "r") as file:
    allText = file.read()
    RFID_Number = list(map(str, allText.split()))

# with open("Words.txt", "r") as file:
#     allText = file.read()
#     Numbers = list(map(str, allText.split()))

for i in range(0, 10):
    User_RFID = random.choice(RFID_Number)

    New_URL = Main_URL + "?RFID_Number=" + User_RFID
    print(New_URL)
    webbrowser.open(New_URL)
    sleep(0.7)
