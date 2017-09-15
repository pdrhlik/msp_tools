Tato sada programů byla vytvořena v rámci miniprojektu na [MTI FM TUL](http://www.fm.tul.cz/ustavy/ustav-mechatroniky-a-technicke-informatiky/o-ustavu). Cílem je usnadnění nahrávání R Shiny aplikací na vlastní server.

Oficiální možnost nahrávání je k dispozici pouze skrze [RStudio Connect](https://www.rstudio.com/products/connect/), který je zpoplatněný. Zdarma se dá využít pouze k nahrávání na [shinyapps.io](http://www.shinyapps.io/), ale ne na vlastní server.

Jediná alternativa nahrávání na vlastní server, která je zdarma, je ruční kopírování souborů.

# msp_upload
Program nahraje R Shiny aplikaci na vlastní server. Program se volá z kořenového adresáře Shiny aplikace, která musí obsahovat konfigurační soubor **config.cfg**.

Příklad použití:
```bash
cd $SHINY_APP_DIRECTORY
msp_upload
# $USERNAME@$SERVER's password:
# $USERNAME@$SERVER's password:
# image.jpg	100%	400		0.4KB/s   00:00
# app.R	    100%    1579    1.5KB/s   00:00
# Project at: http://$SERVER/users/$USERNAME/$PROJECT_NAME
```

## Konfigurační soubor
Každý Shiny projekt musí mít vyplněný konfigurační soubor **config.cfg** v kořenovém adresáři. Repozitář obsahuje šablonu, kterou je potřeba vyplnit.

* **SERVER:** URL adresa serveru.
* **USERNAME:** Uživatelské jméno, jehož účet je na serveru registrovaný.
* **REMOTE_DIR:** Adresář, do kterého se složka s aplikací nahraje. Defaultně je nastavený na `/home/$USERNAME/ShinyApps`

```
SERVER=""
USERNAME=""
REMOTE_DIR=/home/$USERNAME/ShinyApps
```

# msp_adduser
**Program je určen pouze pro administrátory serveru.**

Program vytvoří uživatele, vygeneruje mu heslo a správnou adresářovou strukturu pro nahrávání Shiny aplikací. Program se musí volat ze stejného adresáře, v kterém je soubor **template.html**. Ten slouží k vygenerování html šablony stránky nově vytvořeného uživatele.

Příklad použití:
```bash
msp_adduser username
```

# msp_deluser
**Program je určen pouze pro administrátory serveru.**

Program kompletně smaže uživatele včetně domácího adresáře.

Příklad použití:
```bash
msp_deluser username
```

# Kontakt

[Patrik Drhlík](http://www.fm.tul.cz/personal/patrik.drhlik)

[Vratislav Žabka](http://www.fm.tul.cz/personal/vratislav.zabka)
