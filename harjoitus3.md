# Harjoitus 3
## a) Tee tämä tehtävä Markdownilla

Linkki .md-tiedostoon

    Ajetaan peruskomento
        sudo apt-get update
    Asennetaan git
        sudo apt-get install git -y

Luodaan verkossa Githubiin tunnukset/kirjaudutaan sinne sisään ja luodaan uusi repositorio. Laitoin nimeksi PH3, tein siitä julkisen ja valitisin, että repositorioon luodaan README tiedosto. Lisenssiksi valitsin GNU GPL v3.0.
Tämän jälkeen palataan terminaaliin.

    Määritetään config tiedot gittiin
        git config –global user.email ”omasäpo”
        git config –global user.name ”nimesi”
    Kloonataan Githubista repositorio komennolla
        git clone https://github.com/VilleMaentyranta/PH3.git
    Siirrytään kansioon
        cd /PH3/
    Luodaan harjoitus3.md tiedosto ja muokataan sitä haluamalla tavalla.
        nano harjoitus3.md
    Annetaan seuraava komento, joka päivittää tiedoston Githubiin
        git add . && git commit; git pull && git push
    Kurkataan Githubista, että tiedosto on varmasti päivittynyt sinne ja sehän on. 

## Näytä omalla git varastollasi esimerkit

Aluksi ajoin git log -komennon, joka näyttää lokitiedot Gitissä tapahtuneista muutoksista

Git diff -komento näyttää muutokset, joita ei ole vielä add-komennolla lisätty Gittiin

Git blame tiedostonnimi -komento näyttää, kuka on tehnyt muutoksia, milloin, mille riville ja mikä muutos on tehty.

## Tee tyhmä muutos gittiin

Lisäsin harjoitus3.md tiedostoon uuden tekstirivin, sisältäen tyhmää tekstiä. Ajoin tämän jälkeen git reset — hard -komennon, joka kumosi muutokset ja palautti tiedoston takaisin viimeisimpään muotoon

## Tee uusi salt-moduuli

Päätin asentaa minionille htopin.

    Luodaan kansio htop
        sudo mkdir htop
    luodaan kansioon tiedosto init.sls, johon kirjoitetaan
        sudo nano /srv/salt/htop/init.sls
            htop:
            pkg.installed
    Otetaan moduuli käyttöön orjille
        sudo salt ’*’ state.apply htop


