def sezar_atbash_sifrele(metin):
    # Sezar şifreleme anahtarı
    anahtar = 3

    # Sezar şifrelemesi uygulanıyor
    sifreli_metin = ""
    for harf in metin:
        if harf.isalpha():
            # Sadece harfler şifrelenir, diğer karakterler aynı kalır
            yeni_kod = ord(harf) + anahtar
            if harf.isupper():
                if yeni_kod > ord('Z'):
                    yeni_kod -= 26
                elif yeni_kod < ord('A'):
                    yeni_kod += 26
            elif harf.islower():
                if yeni_kod > ord('z'):
                    yeni_kod -= 26
                elif yeni_kod < ord('a'):
                    yeni_kod += 26
            sifreli_metin += chr(yeni_kod)
        else:
            sifreli_metin += harf

    # Atbash Cipher uygulanıyor
    atbash_sifreli_metin = ""
    for harf in sifreli_metin:
        if harf.isalpha():
            yeni_kod = ord('a') + ord('z') - ord(harf.lower())
            if harf.isupper():
                atbash_sifreli_metin += chr(yeni_kod).upper()
            else:
                atbash_sifreli_metin += chr(yeni_kod)
        else:
            atbash_sifreli_metin += harf

    
    print(atbash_sifreli_metin)
    


mesaj = input("şifrelencek metin : ")
sezar_atbash_sifrele(mesaj)