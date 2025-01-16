# XRechnungValidator
XRechnung Validator nach Deutschem Standard. 

Validator von Kosit https://github.com/itplr-kosit.
In der Datei XRechnungValidator.contaniner wird eine Docker Datei beschrieben die die nötigen Pakete herunterlädt und vorbereitet.
Sodass mit 2 Order Angaben eine schnelle Validierung im CLI Bereich möglich ist.

#  Ausführung

Auf dem auszuführendem Rechner ist nach wahl Podman oder Docker zu installieren.
Meine wahl ist hier Podman

Zuerst muss das Image gebaut werden.
Hier ist es aktuell noch wichtig das der Befehel entweder im Order der Datei ausgeführt wird oder der Pfad der .contianer Datei angegeben wird.
podman build -t xrechnung_validator -f XRechnungValidator.contaniner .

# bash Skript
podman run --rm \
-v dein-pfad/report\:/app/validator/reports \
-v dein-pfad//xrechnung/testfiles\:/app/validator/testfiles \
-t xrechnung_validator 

# ps Skript
podman run --rm -v dein-pfad\report\:/app/validator/reports -v dein-pfad\testfiles\:/app/validator/testfiles -t xrechnung_validator 

