# monstersalat.de

WIP Jekyll Website for monstersalat.de. By Maren Siegel.


# Notizen

- ```bundle exec jekyll serve```
- ```bundle exec jekyll build```
* http://jekyllrb.com/
* http://jekyllrb.com/docs/usage/


# Domain

* [Setting up a www subdomain](https://help.github.com/articles/setting-up-a-www-subdomain/)
 - IST: `CNAME` to `tordans.github.io`
* [Setting up an apex domain](https://help.github.com/articles/setting-up-an-apex-domain/)
 - SOLL: `A` to `192.30.252.153`
 - IST: Wir können den A Record nicht setzen, das der Hoster immer automatisch einen nicht löschbaren *.-A-Record setzt. Das sorgt für Probleme (siehe unten). Daher liegt jetzt auf dem Server eine `.htaccess`-Datei die den Redirect durchführt (siehe Ordner "_redirct-…" hier).
 - Warum wir keinen *.-A-Record verwenden dürfen: "Danger: Do not use wildcard DNS records (e.g. *.example.com) with GitHub Pages! A wildcard DNS record will allow anyone to host a GitHub Pages site at one of your subdomains." - https://help.github.com/articles/setting-up-a-custom-subdomain/
