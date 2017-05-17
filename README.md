## Koodiaapinen-MOOC pedagoginen suunnittelutehtävä ##

Tämä dokumentti on yksi sovellus pedagogiseen suunnittelutehtävään Koodiaapinen-MOOC kurssille.

http://koodiaapinen.fi/mooc/

*Miika Pietilä *

***

# Rakennetaan pyörillä kulkeva robotti #

Kahden tunnin oppitunti on toinen kerta viidestä robottien rakentamisen kokonaisuutta. Ensimmäisellä kerralla on tutustuttu Arduino-ympäristöön ja kerrattu ohjelmoinnin perusteita.

1. kerta: Johdanto, tutustuminen ArduinoIDEen, robotin toiminnan perusteita, hieman mekaniikkaa ja elektroniikkaa.

1. **kerta: Laitetaan LED vilkkumaan ja opitaan kuinka ohjelmointi vaikuttaa fyysisiin laitteisiin eli tässä tapauksessa Arduino-kehityslautaan.**

1. kerta: Rakennetaan robotin mekaniikka ja elektroniikkakytkennät.

1. kerta: viimeistellään ohjelmointia ja mekaniikkaa, personoidaan robottia maalaamalla tai muuten koristelemalla.

1. kerta: Robottien tehtävärata. Edellisellä kerralla on jo kokeiltu robottia radalla ja alussa kokeillaan robottien suoriutumista radalla. Pohditaan yhdessä ja pienemmissä ryhmissä mahdollisia parannuksia robottiin. Mitä on opittu ja miten sitä voisi hyödyntää.

Robotin rakentaminen on mahdollista yhdistää teknisiin töihin ainakin elektroniikan ja mekaniikan osalta.

## Johdanto ##

Kahden tunnin opetuskokonaisuus hyödyntäen Arduino-kehitysympäristöä. Edistyneemmät oppilaat pääsevät esimerkkien avulla pidemmälle robotin ohjaukseen ja kaikki kykenevät vilkuttamaan LED-valoa haluamallaan tavalla.

Tällä ohjelmoinnin aloituskerralla perehdytään myös hieman mikrokontrollerin toimintaan ja elektroniikaan. Tavoitteena luoda alustavaa ymmärrystä sille miksi sähkölaitteen eli LEDin saa ohjelmallisesti kytkettyä päälle ja pois.

Tuntien etenemiseen vaikuttaa huomattavasti ryhmän ominaisuudet ja kyvyt. Tämä suunnitelma on tehty koodauskerhoa ajatellen, mutta paikoitellen kerrataan hyvin yksinkertaisia asioita ja toisinaan asiat voivat olla hyvin edistyneitä.

## Esitiedot ##

Vaatimuksena opetuksen sujuvuudelle esitietona on jonkinlainen käsitys ohjelmoinnista ja ohjelmointiin liittyvistä käsitteistä ja toimintamalleista. Opetus sopii alakoulun loppupuolella koodauskerhoon tai muuten harrastuneiden kesken hyvin tai yläkoulussa kaikille.

## Oppimistavoitteet ##

Kokonaisuutena tavoite on saada robotti liikkumaan halutulla tavalla. Tämän tunnin tavoitteena on luoda oppilaalle tavoite liikuttaa robottia. Tavoitteen saavuttamiseksi opitaan Arduinon ohjelmointia ja elektroniikan kytkentöjä. Ryhmästä riippuen määritellään sähkötekniset ja mekaaniset tavoitteet.


## Työvälineet ja opetusmenetelmät ##

Ohjelmointiin käytetään paikallisesti asennettua Arduino-ohjelmistoa. Tämän lisäksi käytetään Arduino/Genuino Uno tai Arduino/Genuino Leonardo elektroniikka-alustaa. Robotin pyörien pyörittämiseen käytetään servoja ja käyttövoima robotille tarjotaan usb-varateholähteestä.

Edistyneemmille oppilaille on tarjolla myös erilaisia antureita ja sensoreita, joita voi robotin yhteydessä hyödyntää. Ultraäänellä toimiva etäisyyssensori opettaa myös kaikuluotaustekniikan toimintaperiaatteen.

Edellisellä kerralla on kerrattu ohjelmoinnin perusteita ja pohdittu yhdessä robotin liikuttamiseen tarvittavia toiminnallisuuksia ja funktioita. Oppilaat voivat tuntea ihmisrobottiohjelmointiharjoituksen tai kilpikonnan ohjelmoinnin. Tämä yhteneväisyys on hyvä tuoda esille tunnin aikana ja pohtia aikaisemmin ilmenneitä haasteita tai onnistumisia. Fyysisen elektronisen robotin liikuttaminen on hyvin samankaltaista.


Oppilaat ovat motivoituneita saamaan robotin liikkumaan ja haluavat päästä annettuihin tavoitteisiin. Ryhmän koosta riippuen voi olla tarkoituksenmukaista rakentaa robottia pareittain, jolloin toteutuu hieman [pair programming](https://en.wikipedia.org/wiki/Pair_programming) -ajatusta.


## Arviointi ##

Tavoitteen mukaisesti ledin vilkuttaminen omaan tahtiin on vähimmäisvaatimus. Etenemisen kannalta hyvä suoritus on servojen pyörittäminen oman ohjelman mukaisesti ja pohdintaa robotin ohjauksen toteuttamiseen liittyvistä vaatimuksista.

Oppilaat vertailevat ohjelmointiratkaisujaan keskenään ja pohtivat eroja toteutuksissaan.

## Turtle-ohjelmointi ##

Kerrataan turtle-ohjelmoinnin peruskäsitteitä ja pohditaan soveltamista robotin liikuttamiseen.

```python
# piirretään neliö
turtle.forward(50)
turtle.left(90)
turtle.forward(50)
turtle.left(90)
turtle.forward(50)
turtle.left(90)
turtle.forward(50)
turtle.left(90)
```

## Arduino-ohjelmointi

Oppilaille esitetään perustiedot Arduinosta ja mikrokontrollerista ja elektroniikasta. Tällä tunnilla oleellista on ymmärtää Arduino-kehityslaudan olevan minikokoinen yksinkertainen tietokone ja oppia ohjelmoimaan Arduino tekemään tarvittavia asioita.

**Pohdintaa: Missä muualla on mikrokontrollereita**

Arduinoon voi liittää muita laitteita kiinni i/o-liitäntöjen kautta ([input/output](https://en.wikipedia.org/wiki/Input/output), sisään/ulos). Robottia varten pohditaan tarvittavia i/o-tarpeita ja päästään toivottavasti tulokseen, että moottoreita varten tarvitaan ohjaussignaali. Ryhmästä riippuen voi syventyä pidemmälle analogisiin ja digitaalisiin signaaleihin ja [pulssinleveysmodulaatioon (PWM)](https://fi.wikipedia.org/wiki/Pulssinleveysmodulaatio).

Arduino-ohjelmointi aloitetaan aina [LEDin vilkuttamisella](https://www.arduino.cc/en/tutorial/blink) käyttäen esimerkkien joukosta löytyvää ensimmäistä koodilistausta Blink.


```Arduino
// setup suoritetaan kerran Arduinon käynnistyessä tai resetin
// jälkeen.
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);   // määritellään LED_BUILTIN
                                  // ulostuloksi.
}

// loop-funktio suoritetaan jatkuvasti, ikuinen loop.
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // LED päälle
  delay(1000);                       // odotetaan sekunti
  digitalWrite(LED_BUILTIN, LOW);    // LED pois päältä
  delay(1000);                       // odotetaan sekunti
}
```
Blink-koodi löytyy suoraan Arduinon esimerkeistä, mutta yleensä haasteeksi muodostuu koodin siirtäminen toimivassa muodossa mikrokontrollerille eli Arduino-kehityslaudalle. Arduino käyttää c++:n kaltaista käännettävää ohjelmointikieltä. Koodi on käännettävä ennen siirtämistä mikrokontrolleriin.


1. Käännös/verify, compile (ctrl+r)
1. Siirto/upload (ctrl+u)

Koodin syntaksin oikeellisuutta voi kokeilla Arduinon verify/compile -toiminnolla. Yleensä virhetilanteet paljastuvat tässä vaiheessa kirjoitusvirheiksi tai muuten syntaksivirheiksi.

Blink-esimerkkikoodin kanssa ei pitäisi olla ongelmia kääntämisen kanssa. Seuraavassa vaiheessa ilmenee usein ongelmia, eli Arduino-kehityslaudan kytkeminen USB-kaapelilla tietokoneeseen ja käännetyn ohjelman siirtäminen mikrokontrollerille. ArduinoIDE:n asetuksista tarvitsee ongelmatilanteissa varmistaa oikea kehitysalusta/board ja portti/port.

Blink-esimerkin lopulta toimiessa Arduino-kehityslaudalla voivat oppilaat kokeilla tehdä muutoksia koodiin ja katsoa miten muutokset vaikuttavat. Tässä vaiheessa todennäköisesti aikaa ei ole enää paljoa jäljellä, riippuu asioiden onnistumisesta ja tietokoneiden yhteistyöhalukkuudesta.

**Tavoite: LED vilkuttamaa SOS-tunnusta morsettamalla.**

Ideaalisessa tilanteessa Blink-esimerkkiin ja SOS-koodin aikaansaamiseksi ei kulu koko käytettissä oleva aika ja on mahdollista kokonaisuutena päästä robotin liikuttamiseen käytettävän servon ohjaukseen. Nopeammat ja edistyneemmät varmasti pääsevät joka tapauksessa servoon asti.

## Servo

Robotissa on kaksi itsenäistä vetävää pyörää, yksi kummallakin sivulla. Pyörää pyöritetään käyttäen jatkuvatoimista RC-servoa.

Servon liikettä ohjataan Arduinolla tuotetulla pulssinleveysmodulaatiosignaalilla, mutta onneksi Arduinoon löytyy suoraan valmis kirjasto servojen käsittelyyn, ettei tarvitse perehtyä PWM-signaaleihin kovin syvällisesti.

* [Arduino servo esimerkki](https://playground.arduino.cc/Learning/SingleServoExample)

Servon käyttöön tarvittava kirjasto otetaan ohjelmassa käyttöön komennolla

```#include <Servo.h>```

Servolle annetaan ohjauskomentoja käyttäen komentoa `servo.write()`. Servon ohjauskomento ottaa argumenttina vastaan luvun 0-180 väliltä niin, että 0 on täysi vauhti yhteen suuntaan, 90 on pysähdyksissä ja 180 on täysi vauhti toiseen suuntaan. Esimerkiksi `servo.write(90)`  pysäyttää servon. Hieman servoista riippuen 90 ei välttämättä ole keskikohta eli servo ei pysähdy arvolla 90.

Alla oleva esimerkki kiihdyttää, jarruttaa, vaihtaa suuntaa, kiihdyttää ja jarruttaa servoa.

```
#include <Servo.h>

Servo myservo;  // luodaan servo-objekti, vertaus Turtleen.

int speed = 0;  // muuttuja nopeudelle

void setup() {
  myservo.attach(9);  // määritelläänservon datajohdin
                      // olevan kytkettynä pinniin 9.
}

void loop() {
  for(speed = 0; speed < 180; speed += 1) { // 0-180                            
    myservo.write(speed);    // käskytetään servoa nopeudella
    delay(15);               // odotetaan 15ms
  }
  for(speed = 180; speed>=1; speed-=1) {    // 180-0                      
     myservo.write(speed);   // käskytetään servoa nopeudella
     delay(15);              // odotetaan 15ms
  }  
}
```

Servo kytketään niin, että servon maa (GND) kytketään Arduinon GND-pinniin, yleensä musta. Servon tehonsyöttö kytketään Arduinon 5v-pinniin, yleensä punainen. Servon signaalijohdin kytketään Arduinon pinniin 9.

* [Esimerkkikytkentä](https://www.arduino.cc/en/uploads/Tutorial/sweep_BB.png)
* [Esimerkkikytkentä, lisänä AA-paristot](https://upload.wikimedia.org/wikipedia/commons/2/2c/Arduino_servo_sweep.svg)

Tämä kohta on hyvin haastava, aikaavievä ja virhealtis. Tässä kohdassa kannattaa kannustaa oppilaita auttamaan toisiaan ja vaikka robottia ei pareittain tehtäisi on hyvä ajatus vaatia vieruskaveria tarkistamaan kytkennät ennen virtojen kytkemistä. Jos löytyy eriäviä mielipiteitä niin sitten voi ottaa kolmannenkin mielipiteen tai kysyä opettajalta.

Toinen servo kytketään sitten johonkin muuhun PWM-kykyiseen Arduinon pinniin, esimerkiksi pinnin 10.

## Nopeimmille

* https://playground.arduino.cc/Main/UltrasonicSensor
* http://robotit.hacklab.fi

## Lopputulos

Jos kahden tunnin jälkeen servot pyörivät halutulla tavalla niin, että tuota servo-esimerkkiäkin on jo muokattu voidaan olla kaikki hyvin tyytyväisiä aikaansaannoksiin. Kahden tunnin jälkeen on opittu ohjelmoinnin perusteita, viety turtle-ohjelmointi pykälän pidemmälle fyysisen turtlen ohjaamisen suuntaan. Ryhmästä riippuen on mahdollisesti opittu myös elektroniikkaa, LEDin toimintaa, mikrokontrollereiden perusteita, kaikuluotaimen toimintaa käytännössä ja mekaniikkaa.

Kokonaisuutena idea on kannustaa oppimaan tekemällä ja kokeilemalla. Usein ryhmästä löytyy myös muutama innokas apuopettaja ja siihen kannattaa ehdottomasti kannustaa. Vertaisoppimista ja yhdessä tekemistä.
