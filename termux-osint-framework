import os
import sys
import subprocess

# Renk Tanımlamaları
GREEN = '\033[92m'
BLUE = '\033[94m'
YELLOW = '\033[93m'
RED = '\033[91m'
PURPLE = '\033[95m'
CYAN = '\033[96m'
END = '\033[0m'
BOLD = '\033[1m'
UNDERLINE = '\033[4m'

def clear():
    os.system('clear')

def header():
    print(f"{CYAN}{BOLD}" + "="*50)
    print("      CODZA OSINT FRAMEWORK v1.0    ")
    print("="*50 + f"{END}\n")

# --- OSINT MASTER KÜTÜPHANESİ ---
OSINT_DATA = {
    "1": {
        "title": "📚 GENEL OSINT FRAMEWORKS",
        "desc": "Bilgi toplama sürecinin ana haritaları ve devasa araç listeleri.",
        "tools": [
            ("OSINT Framework", "https://osintframework.com/"),
            ("IntelTechniques Tools", "https://inteltechniques.com/tools/index.html"),
            ("Cyber-Intelligence Center", "https://cyber-intelligence.eu/")
        ]
    },
    "2": {
        "title": "🔓 ŞİFRE & HASH KIRMA",
        "desc": "Sızmış verileri ve hash'lenmiş şifreleri (MD5, SHA vb.) deşifre eder.",
        "tools": [
            ("CrackStation (Hash DB)", "https://crackstation.net/"),
            ("Hashkiller (Big List)", "https://hashkiller.io/"),
            ("Online ZIP Password Cracker", "https://www.lostmypass.com/file-types/zip/"),
            ("MD5Decrypt World", "https://md5decrypt.net/")
        ]
    },
    "3": {
        "title": "🔡 ENCODING & STEGANO",
        "desc": "Base64, Hex ve karmaşık steganografi yöntemlerini çözer.",
        "tools": [
            ("CyberChef (The King)", "https://gchq.github.io/CyberChef/"),
            ("Base64 Decode/Encode", "https://www.base64decode.org/"),
            ("D-Code (All Solvers)", "https://www.dcode.fr/"),
            ("Frank.fr (Hidden Text)", "https://frank.fr/")
        ]
    },
    "4": {
        "title": "🌐 DOMAIN & NETWORK",
        "desc": "Domain geçmişi, WHOIS, DNS ve IoT (Shodan) araştırması.",
        "tools": [
            ("WHOIS Lookup", "https://www.whois.com/whois/"),
            ("DNS Dumpster", "https://dnsdumpster.com/"),
            ("Shodan IoT Search", "https://www.shodan.io/"),
            ("crt.sh Certificate Search", "https://crt.sh/"),
            ("Wayback Machine", "https://web.archive.org/")
        ]
    },
    "5": {
        "title": "🕵️ KİŞİ & SOSYAL MEDYA",
        "desc": "İsim, Mail, Tel veya Fotoğraf üzerinden kimlik tespiti.",
        "tools": [
            ("Pimeyes (Face Search)", "https://pimeyes.com/en"),
            ("Sherlock (User Search)", "https://sherlock-project.github.io/"),
            ("Epieos (Mail OSINT)", "https://epieos.com/"),
            ("WhatsMyName (Username)", "https://whatsmyname.app/"),
            ("OSINT Industries (Email/Tel)", "https://www.osint.industries/")
        ]
    },
    "6": {
        "title": "🎥 VİDEO ANALİZ & OSINT",
        "desc": "Videolardaki gizli mesajları, sahteciliği ve mekan analizini yapar.",
        "tools": [
            ("InVID Video Verify", "https://www.invid-project.eu/"),
            ("Watch Frame by Frame", "http://www.watchframebyframe.com/"),
            ("Bellingcat Toolkit", "https://docs.bellingcat.com/"),
            ("SunCalc Shadow Search", "https://suncalc.org/")
        ]
    },
    "7": {
        "title": "🎵 SES ANALİZ & STEGO",
        "desc": "Frekans spektrumu (Spektrogram) ve ses içine gizlenmiş veriler.",
        "tools": [
            ("Academo Spectrum Analyzer", "https://academo.org/demos/spectrum-analyzer/"),
            ("Steganography Online", "https://stylesuxx.github.io/steganography/"),
            ("Futureboy Audio Decoder", "https://futureboy.us/stegano/decinput.html"),
            ("Sodaphonic Online Editor", "https://sodaphonic.com/")
        ]
    },
    "8": {
        "title": "🦠 MALWARE & DARK WEB",
        "desc": "Şüpheli link analizi ve Tor ağı (Deep Web) araması.",
        "tools": [
            ("urlscan.io", "https://urlscan.io/"),
            ("VirusTotal Scan", "https://www.virustotal.com/"),
            ("Ahmia (Tor Search Engine)", "https://ahmia.fi/search/"),
            ("Tor.link Gateway", "https://tor.link/")
        ]
    }
}

def sub_menu(choice):
    category = OSINT_DATA[choice]
    while True:
        clear()
        header()
        print(f"{YELLOW}--- {category['title']} ---{END}")
        print(f"{CYAN}[README]: {category['desc']}{END}\n")
        
        for i, (name, _) in enumerate(category['tools'], 1):
            print(f"{GREEN}[{i}] {name}{END}")
        
        print(f"\n{RED}[0] Geri Dön{END}")
        
        sub_choice = input(f"\n{BOLD}Seçiminiz >> {END}")
        
        if sub_choice == "0":
            break
        try:
            index = int(sub_choice) - 1
            if 0 <= index < len(category['tools']):
                name, url = category['tools'][index]
                print(f"\n{BLUE}[*] Hedef: {name}{END}")
                # Linki tıklanabilir ve belirgin bir şekilde yazdırıyoruz
                print(f"{PURPLE}{BOLD}[LİNK] >> {UNDERLINE}{url}{END}")
                
                # Termux'ta termux-open varsa otomatik açmayı dener
                try:
                    subprocess.run(["termux-open", url], stderr=subprocess.DEVNULL)
                except:
                    pass
                
                input(f"\n{YELLOW}Devam etmek için ENTER basın...{END}")
            else:
                print(f"{RED}[!] Geçersiz numara!{END}")
                os.system("sleep 1")
        except:
            print(f"{RED}[!] Lütfen bir sayı girin!{END}")
            os.system("sleep 1")

def main():
    while True:
        clear()
        header()
        print(f"{YELLOW}Lütfen bir araştırma kategorisi seçin:{END}\n")
        
        for key, value in OSINT_DATA.items():
            print(f"{GREEN}[{key}] {value['title']}{END}")
            
        print(f"\n{RED}[99] Kapat (Exit){END}")
        
        main_choice = input(f"\n{BOLD}CODZA > {END}")
        
        if main_choice == "99":
            print(f"{CYAN}Görüşmek üzere...{END}")
            sys.exit()
        elif main_choice in OSINT_DATA:
            sub_menu(main_choice)
        else:
            print(f"{RED}[!] Hatalı seçim!{END}")
            os.system("sleep 1")

if __name__ == "__main__":
    main()
