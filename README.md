Demek set-cookie \_\_cfduid=87827hf872h3d87h239djidijqoed cookie reverse proxyde ve clientin browserde saxlanilir ki tekrar client servere request atanda hemin cookie baxib clienti hansi servere forward edeceyini teyin edir (modern web app-larda multiple serverler olur hansi ki hamisi eyni kodu dasiyir e.g python kodu,biri cokse digerleri serve elesin deye)
Hemcinin sessionu serverin diskinde tutmag da mentiqsizdi cunki client hemin serverde login olubsa ve hemin server cokerse reverse proxy onu diger servere gonderecek hansi ki onun diskinde clientin session bilgileri yoxdu deye logout olacaq.
Hell yolu olaraq da sessionlari diskden kenarda session servicelerde(redis vs vs) saxlanilir.
Session service down olarsa o up olana kimi heckim login ola bilmez cunki session yaranmiyacag ona gore de herseyin backup-ini dusunmek vacibdir.
Static fayllar (fotolar,js kodu falan filan) da diskde saxlanilmamalidi (eynile session kimi) ona gore de static fayllari saxlamag ucun CDN(content delivery network)-ler istifade edilir.
CDN-ler ise shell upload vulnerabilitilerin qarsisini alir niye sualini verecek olarsaq ,yuklenen reverse shell-in artiq serverle hecbir elaqesi yoxdu(kenardadi,CDN).
Ve hemcinin static dosyanin adi databasede saxlanilir,client hemin dosyani request edende server onun adini database-den goturub cliente verir ve client de gedib onu birbasa CDN-den goturur servere getmeyine hec gerek qalmir.
FIREWALL+REVERSE PROXY=CLOUDFLARE
Ve bizim servere dunyanin coxlu yerinden requestler gelir ve static fayllara access etmeleri lazimdi bunun ucun clientlerin her defe CDN-e getmelerine gerek yoxdu cloudflare goturur onun cache-ni internetdeki butun node-lara qoyur ve clientler static fayllari hemin node-lardan goturur.
DMZ=demilitarized zone
DRS=disastery recovery system (copy of DMZ,like backup)
SSL/TLS reverse proxyde bitir demek ki reverse proxy-ni ele kecirsek butun traffici goreciyik.
CDN servisini 3rd partyden alarsaq ve hemin 3rd party hack-lenerse bu zaman da hacker istediyi js kodunu CDN-e yerlesdirecek ve clientlerin browserlerini ele kecirmis olacaq.




