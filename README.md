def atm():
    pin = "2579"        # sadece bu pin çalışacak
    Bakiye1 = 150000

    print("Hoşgeldiniz") 

    # PIN kontrolü
    for attempt in range(3):
        sifre = input("Şifre Giriniz: ")
        if sifre == pin:
            print("Şifre Onaylandı")
            break
        else:
            print("Şifre Hatalı")
    else:
        print("3 defa şifreyi yanlış girdiniz. Kartınız bloke oldu.")
        return

    # Menü
    while True:
        print("\nMENÜ")
        print("1 - Bakiye Sorgulama")
        print("2 - Para Çekme")
        print("3 - Para Yatırma")
        print("4 - Çıkış")
        
        sec = input("Seçiniz: ")
    
        if sec == "1":
            print(f"Bakiyeniz: {Bakiye1} TL")

        elif sec == "2":
            cek = int(input("Çekmek istediğiniz tutar: "))
            if cek > Bakiye1:
                print("Yetersiz Bakiye")
            elif cek == Bakiye1:
                print(f"{Bakiye1} TL çekildi, bütün bakiyenizi çektiniz.")
                Bakiye1 = 0
                print(f"Kalan bakiyeniz: {Bakiye1} TL")
            else:
                Bakiye1 -= cek
                print(f"{cek} TL çektiniz.")
                print(f"Kalan bakiyeniz: {Bakiye1} TL")

        elif sec == "3":
            yatir = int(input("Yatırmak istediğiniz tutar: "))
            Bakiye1 += yatir
            print(f"{yatir} TL yatırıldı.")
            print(f"Yeni bakiyeniz: {Bakiye1} TL")

        elif sec == "4":
            print("İyi günler dileriz.")
            break

        else: 
            print("Geçersiz işlem yaptınız. Lütfen tekrar deneyiniz.")
# Programı çalıştır
atm()
