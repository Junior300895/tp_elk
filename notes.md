## commande de démarrage des serveurs

- elasticsearch.bat
- kibana.bat

## 1.  récupération du TP
git clone -b step-00 https://github.com/zouheircadi/hol-elastic-devoxxfr.git

## création d'index
POST hol_devoxxfr_11/_bulk
{ "index": { "_id": 1 }}
{"app_name" : "Photo Editor", "category" : "ART-AND-DESIGN", "last_updated" : "2018-01-06","rating" : 4.1}
{ "index": { "_id": 2 }}
{ "app_name" : "YouTube Kids", "category" : "FAMILY", "last_updated" : "2018-08-02", "rating" : 4.5}
{ "index": { "_id": 3 }}
{ "app_name" : "Block Puzzle Classic Legend !","category" : "GAME", "last_updated" : "2018-07-22", "rating" : 4.7}
{ "index": { "_id": 4 }}
{ "app_name" : "Marble Woka Woka 2018 - Bubble Shooter Match 3", "category" : "GAME", "last_updated" : "2018-08-02","rating" : 4.6}
{ "index": { "_id": 5 }}
{ "app_name" : "QR Code Reader", "category" : "TOOLS", "last_updated" : "2016-03-15", "rating" : 4.0}
{ "index": { "_id": 6 }}
{ "app_name" : "Diabetes:M", "category" : "MEDICAL", "last_updated" : "2018-07-31", "rating" : 4.6}   

## creation banque
## 2. TP BANQUE 
POST bank/_bulk
{ "create":{ } }
{ "account_number":1,"balance":39225,"firstname":"Amber","lastname":"Duke","age":32,"gender":"M","address":"880 Holmes Lane","employer":"Pyrami","email":"amberduke@pyrami.com","city":"Brogan","state":"IL" }
{ "create":{ } }
{ "account_number":6,"balance":5686,"firstname":"Hattie","lastname":"Bond","age":36,"gender":"M","address":"671 Bristol Street","employer":"Netagy","email":"hattiebond@netagy.com","city":"Dante","state":"TN" }
{ "create":{ } }
{ "account_number":13,"balance":32838,"firstname":"Nanette","lastname":"Bates","age":28,"gender":"F","address":"789 Madison Street","employer":"Quility","email":"nanettebates@quility.com","city":"Nogal","state":"VA" }
{ "create":{ } }
{ "account_number":18,"balance":4180,"firstname":"Dale","lastname":"Adams","age":33,"gender":"M","address":"467 Hutchinson Court","employer":"Boink","email":"daleadams@boink.com","city":"Orick","state":"MD" }
{ "create":{ } }
{ "account_number":20,"balance":16418,"firstname":"Elinor","lastname":"Ratliff","age":36,"gender":"M","address":"282 Kings Place","employer":"Scentric","email":"elinorratliff@scentric.com","city":"Ribera","state":"WA" }
{ "create":{ } }
{ "account_number":25,"balance":40540,"firstname":"Virginia","lastname":"Ayala","age":39,"gender":"F","address":"171 Putnam Avenue","employer":"Filodyne","email":"virginiaayala@filodyne.com","city":"Nicholson","state":"PA" }
{ "create":{ } }
{ "account_number":32,"balance":48086,"firstname":"Dillard","lastname":"Mcpherson","age":34,"gender":"F","address":"702 Quentin Street","employer":"Quailcom","email":"dillardmcpherson@quailcom.com","city":"Veguita","state":"IN" }
{ "create":{ } }
{ "account_number":37,"balance":18612,"firstname":"Mcgee","lastname":"Mooney","age":39,"gender":"M","address":"826 Fillmore Place","employer":"Reversus","email":"mcgeemooney@reversus.com","city":"Tooleville","state":"OK" }
{ "create":{ } }
{ "account_number":44,"balance":34487,"firstname":"Aurelia","lastname":"Harding","age":37,"gender":"M","address":"502 Baycliff Terrace","employer":"Orbalix","email":"aureliaharding@orbalix.com","city":"Yardville","state":"DE" }
{ "create":{ } }
{ "account_number":49,"balance":29104,"firstname":"Fulton","lastname":"Holt","age":23,"gender":"F","address":"451 Humboldt Street","employer":"Anocha","email":"fultonholt@anocha.com","city":"Sunriver","state":"RI" }


## curl with certificate 
Import-Certificate -FilePath "C:/Users/aliounebada.ndoye/Documents/work_dir/ELK/logstash-8.6.2/config/certs/http_ca.crt" -CertStoreLocation cert:\CurrentUser\Root
OR
Import-Certificate -FilePath "C:/Users/aliounebada.ndoye/Documents/work_dir/ELK/logstash-8.6.2/config/certs/http_ca.crt" -CertStoreLocation Cert:\LocalMachine\Root


curl -XPUT --ssl-no-revoke -fL https://localhost:9200/_bulk -H "Content-Type: application/json" --data-binary @movies_elastic.json

curl --user 'elastic:FgIe+2GRVYxfJWK-YT-b' --ssl-no-revoke -fL https://localhost:9200/_bulk -XPUT -H "Content-Type: application/json" --data-binary @movies_elastic.json


## liens intéressants
https://openclassrooms.com/fr/courses/4462426-maitrisez-les-bases-de-donnees-nosql/6735351-entrainez-vous-a-extraire-lessence-dune-base-de-donnees

https://www.elastic.co/guide/en/welcome-to-elastic/current/getting-started-general-purpose.html ==> tp bank

https://www.elastic.co/fr/blog/how-to-keep-elasticsearch-synchronized-with-a-relational-database-using-logstash ==> chargement données sur elastic depuis une base de données mysql

https://www.linkedin.com/pulse/elasticsearch-partie-2-les-requ%C3%AAtes-ali-ibrahim-junior/ ==> requetes poussées sur elascticsearch

https://learn.microsoft.com/en-us/powershell/module/pki/import-certificate?view=windowsserver2022-ps  ==> configuration curl with certificate