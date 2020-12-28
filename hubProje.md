import time
import sys

dersler = ["1:Matematik", "2:Fizik", "3:Kimya", "4:Türkçe", "5:Tarih", "6:Mantık"]
dersSayisi = len(dersler)
ogrDersler = []

#Login Bölümü
print("Giriş için 3 deneme hakkınız var")
count=1
while count < 4:
	ad = input("Ad:")
	soyad = input("Soyad:")
	if ad =='Taner' and soyad=='Erdoğan':
		print("Hoşgeldin {} {}" .format(ad, soyad))
		break

	else:
		print('Hatalı bilgi tekrar deneyin.')
		print("{}. denemeniz" .format(count))
		count += 1
		if count == 4:
			print('3 denemeniz de başarısız oldu! Bye!')
			sys.exit(1)

#Ders Şeçim Bölümü
print("Lütfen Listeden en az 3, en fazla 5 ders seçiniz")
print(dersler)
time.sleep(1)


#1
count1 = 0
while count1 < 5:
	dersSecim = int(input("Ders seçiminizi yapınız (1-6):"))
	if(dersSecim == 1):
		if ('1:Matematik' in ogrDersler):
			print("\n *Matematik dersini zaten seçmişsiniz")
			count1 -= 1
		else:
			ogrDersler.append(dersler[0])
			print("\n=> {} dersi başarıyle eklendi \n".format(dersler[0]))
			print(ogrDersler),


	if (dersSecim == 2):
		if ('2:Fizik' in ogrDersler):
			print("\n *Fizik dersini zaten seçmişsiniz")
			count1 -= 1
		else:
			ogrDersler.append(dersler[1])
			print("\n=> {} dersi başarıyle eklendi \n".format(dersler[1]))
			print(ogrDersler)


	if (dersSecim == 3):
		if ('3:Kimya' in ogrDersler):
			print("\n *Kimya dersini zaten seçmişsiniz")
			count1 -= 1
		else:
			ogrDersler.append(dersler[2])
			print("\n=> {} dersi başarıyle eklendi \n".format(dersler[2]))
			print(ogrDersler)


	if (dersSecim == 4):
		if ('4:Türkçe' in ogrDersler):
			print("\n *Türkçe dersini zaten seçmişsiniz")
			count1 -= 1
		else:
			ogrDersler.append(dersler[3])
			print("\n=> {} dersi başarıyle eklendi \n".format(dersler[3]))
			print(ogrDersler)


	if (dersSecim == 5):
		if ('5:Tarih' in ogrDersler):
			print("\n *Tarih dersini zaten seçmişsiniz")
			count1 -= 1
		else:
			ogrDersler.append(dersler[4])
			print("\n=> {} dersi başarıyle eklendi \n".format(dersler[4]))
			print(ogrDersler)


	if (dersSecim == 6):
		if ('6:Mantık' in ogrDersler):
			print("\n *Mantık dersini zaten seçmişsiniz")
			count1 -= 1
		else:
			ogrDersler.append(dersler[5])
			print("\n=> {} dersi başarıyle eklendi \n".format(dersler[5]))
			print(ogrDersler)


	count1 += 1
	print("Toplam {} ders aldınız".format(len(ogrDersler)))
	if count1 < 3:
		print("En az 3 ders seçmeniz gerekmektedir aksi takdirde kalmış sayılacaksınız")
	if  count1 >= 3 and \
		count1< 5:
		print("5 ders seçme hakkınız var")
	if count1 == 5:
		print("***Tebrikler. Ders seçimini tamaladınız***")
		ogrDersler.sort()
		print("Kayıt olduğunuz dersler {}" .format(ogrDersler))
		print("Yukarıda, aldığınız derslerden 1 tanesinin sınavına girmek için seçiniz")
		sinavDersSecim = int(input("Sınav Ders seçiminizi yapınız (1-6):"))

		if (sinavDersSecim == 1):
			print("\n*Sınava Gireceğiniz ders Matematik")

		if (sinavDersSecim == 2):
			print("\n*Sınava Gireceğiniz ders Fizik")

		if (sinavDersSecim == 3):
			print("\n*Sınava Gireceğiniz ders Kimya")

		if (sinavDersSecim == 4):
			print("\n*Sınava Gireceğiniz ders Türkçe")

		if (sinavDersSecim == 5):
			print("\n*Sınava Gireceğiniz ders Tarih")

		if (sinavDersSecim == 6):
			print("\n*Sınava Gireceğiniz ders Mantık")

print("Notlarınızı Giriniz:")

while True:
    try:
        vize = int(input('Vize: '))
    except ValueError:
        print("Rakam giriniz")
        exit(-1)
    if 0 < vize <=100:
        break
    else:
        print("Vize notu 1-100 arasında olmalıdır")

while True:
    try:
        proje = int(input('Proje: '))
    except ValueError:
        print("Rakam giriniz")
        exit(-1)
    if 0 < proje <=100:
        break
    else:
        print("Proje notu 1-100 arasında olmalıdır")

while True:
    try:
        final = int(input('Final: '))
    except ValueError:
        print("Rakam giriniz")
        exit(-1)
    if 0 < final <=100:
        break
    else:
        print("Final notu 1-100 arasında olmalıdır")


toplam = vize * 0.3 + final * 0.5 + proje * 0.2

if 89 < toplam:
	harfNotu = "AA"
elif 69 < toplam < 90:
	harfNotu = "BB"
elif 49 < toplam < 70:
	harfNotu = "CC"
elif 29 < toplam < 50:
	harfNotu = "DD"
elif toplam< 30:
	harfNotu = "FF"

print("Ders sonucunuz: ({}) {}".format(harfNotu, round(toplam, 2)))
if harfNotu == 'FF':
	print("Kaldınız!")
else:
	print("Tebrikler Geçtiniz.")
