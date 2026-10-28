# Testitapaukset

Kaikki tapaukset on ajettu automaattisesti selaimessa (Playwright) paikallisessa hakutilassa.

| # | Syöte | Odotettu toiminta | Mitä testaa |
|---|---|---|---|
| 1 | "mun pankikortti meni poikki pesukoneesa, paljonko maksa kortin uusimine?" | Vastaus: kortin uusimisen hinta + painike *Tilaa uusi kortti* | Kirjoitusvirheiden sieto |
| 2 | "voitko ohjata minut suoraan siihen mistä kortin voi tilata" | Avaa mobiilipankin tilausnäkymän automaattisesti | Ohjauspyyntö |
| 3 | "vie minut sinne" (edellisen jälkeen) | Avaa edellisen aiheen näkymän | Keskustelun konteksti |
| 4 | "apua mun kortti varastettiin kaupungilla!" | Kiireellinen ohje, *Sulje kortti nyt* ja soittopainike, haku ohitetaan | Prioriteettisääntö |
| 5 | "paljonko olisi kuukausierä 220 000 € lainalle 25 vuodeksi 4,2 % korolla?" | 1 185,67 €/kk, linkki esitäytettyyn hakemukseen | Työkalu (annuiteetti) |
| 6 | "mun hetu on 010190-123X, voitko tarkistaa saldon?" | Henkilötunnus peitetään, ohjaus saldoon | PII-suodatus |
| 7 | "4111 1111 1111 1111 tää kortti ei toimi" | Kortinnumero peitetään | PII-suodatus |
| 8 | "voitko antaa heti sitovan lainapäätöksen 240 000 € asunnolle?" | Ei päätöstä, eskalointi + yhteenveto asiantuntijalle | Eskalointi |
| 9 | "olen tyytymätön palveluun ja haluan tehdä valituksen" | Eskalointi (reklamaatio) | Eskalointi |
| 10 | "kannattaako ostaa nokian osakkeita vai bitcoinia?" | Ei yksilöllistä neuvoa, ajanvarauslinkki | Sijoitusneuvonnan rajaus |
| 11 | "voinko vuokrata pankista tallelokeron?" | "En löytänyt varmaa vastausta", ei arvausta | Hallusinaatioiden esto |
| 12 | "soitti joku pankista ja pyysi tunnuksia" | Huijausohje + *Sulje kaikki kortit* | Turvallisuus |
| 13 | Linkin klikkaus → lomakkeen lähetys | Vahvistus näkyy sovelluksessa ja chatissa viitteen kanssa | Chatin ja sovelluksen integraatio |
| 14 | Suora URL `#/lainat/hae?summa=220000&aika=25` | Hakemus avautuu esitäytettynä | Syvälinkit |

## Havaittu ja korjattu

- "tallelokero" osui aluksi artikkeliin *Talletussuoja*, koska sanojen alku on sama. Korjattu: sanojen pitää jakaa vähintään 60 % pidemmästä sanasta.
- "pankista" sai liikaa painoa, koska se esiintyi vain huijausartikkelissa. Korjattu: yleiset pankkisanat ohitetaan haussa.
