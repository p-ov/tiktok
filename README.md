import requests
import random
print('''
               .-"""-.
             _/-=-.   \
            (_|a a/   |_
             / "  \   ,_)
        _    \`=' /__/
       / \_  .;--'  `-.
       \___)//      ,  \
        \ \/;        \  \
         \_.|         | |
          .-\ '     _/_/
        .'  _;.    (_  \
       /  .'   `\   \\_/
      |_ /       |  |\\
     /  _)       /  / ||
frs /  /       _/  /  //
    \_/       ( `-/  ||
              /  /   \\ .-.
              \_/     \'-'/
                       "
        By xc63 on dc 17fv tik
''')
litters = 'qwertyuiopasdfghjklzxcvbnm1234567890'

id = input("[+] Enter Id : ")
token = input("[+] Enter Bot Token : ")
sessionid = input("Enter your sessionid : ")

hea = {
        'accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'user-agent': 'user-agent: Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html',
        'Cookie': 'sessionid='+sessionid,
    }
while True:
    user = str("".join(random.choice(litters)for x in range(3)))
    tiko = f'https://www.tiktok.com/api/user/detail/?aid=1988&app_language=ar&app_name=tiktok_web&battery_info=0.32&browser_language=ar&browser_name=Mozilla&browser_online=true&browser_platform=MacIntel&browser_version=5.0%20%28Macintosh%3B%20Intel%20Mac%20OS%20X%2010_15_7%29%20AppleWebKit%2F537.36%20%28KHTML%2C%20like%20Gecko%29%20Chrome%2F109.0.0.0%20Safari%2F537.36&channel=tiktok_web&cookie_enabled=true&device_id=7193110014067459586&device_platform=web_pc&focus_state=true&from_page=user&history_len=10&is_fullscreen=false&is_page_visible=true&language=ar&os=mac&priority_region=&referer=&region=SA&screen_height=900&screen_width=1440tz_name=Asia%2FRiyadh&uniqueId={user}&verifyFp=verify_ldvov399_du9goymx_OHxC_4RTw_AEjU_Dth4CFGFw3lR&webcast_language=ar&msToken=f7RQRFGwBsu3WXbrhdLVX9gDRSynM_O_C7U9SX6WNqZqmb0QEsNO6H3dJ10pMAxt24bmyb2eMNPzUpr8w8-6Wx-xAawe1R6vbD6HZdDoWTPL4VOHo6ebwjHadXlUoyhG9ovbpBnhHipd_EWG&X-Bogus=DFSzswVY9D0ANeIIShUJbR/F6qHH&_signature=_02B4Z6wo00001xH2Y0gAAIDCaTiITAKYgosR9mfAAKeo28'
    reqsnd = requests.get(tiko, headers=hea).text
    if '"statusCode":10221,' in reqsnd:
            print(f'{user} ✅')
            requests.post(f"https://api.telegram.org/bot{token}/sendMessage?chat_id={id}&text=USER : {user}\nBy : @r_nng")
    else:
      print(f'{user} ❌ ')
