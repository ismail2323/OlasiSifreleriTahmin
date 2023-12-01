# OlasiSifreleriTahmin
import itertools

uzunluk = int(input("Lütfen şifrenin kaç karakter olduğunu giriniz: "))

karakterler = input("Lütfen şifrenizde kullanılan karakterleri giriniz: ")

tekrar = input("Lütfen şifrenizde kullanılan karakterler tekrar ediyorsa (1) etmiyorsa (2) ye basın")

dosya = open("olasisifreler.txt", "a", encoding="utf-8")

if tekrar == 1:
   kombinasyonlar = list(itertools.product(karakterler, repeat=uzunluk))
   
else:
   kombinasyonlar = list(itertools.permutations(karakterler, uzunluk)) 
   sifre="uptezmwl"
for index, kombinasyon in enumerate(kombinasyonlar):
    dosya.write("".join(kombinasyon)+"\n")
    if kombinasyon == sifre:
        print(index, sifre)

dosya.close()
