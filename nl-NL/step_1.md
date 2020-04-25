Soms moet je gegevens van een website ophalen. Dit kunnen gegevens zijn die door een web-API zijn verstrekt, of het kan gewoon de **HTML** code van de webpagina zijn. Hoe dan ook, de Python-module `requests` maakt deze taak zeer eenvoudig.

- Open IDLE of jouw favoriete programmeeromgeving en maak een nieuw bestand.

- Importeer eerst de module.

    ```python
    import requests
    ```

- Maak een variabele die de URL opslaat waarvan je gegevens wilt ophalen. In dit voorbeeld ga je de Raspberry Pi-startpagina ophalen.

    ```python
    import requests
url = "https://www.raspberrypi.org"
    ```

- Vertel je programma vervolgens om de webpagina op te halen en op te slaan in een variabele. In dit voorbeeld noemen we het `r`.

    ```python
    import requests
url = "https://www.raspberrypi.org"
r = requests.get(url)
    ```

- Voer nu je programma uit. `r` bevat veel informatie. Je kunt het in de Python-shell onderzoeken met behulp van de onderstaande instructies.

- Wanneer je `r` typt, zou je zoiets moeten zien:

    ```python
    >>> r
    <Response [200]>
    ```

- Dit is een **HTTP-antwoordcode**. Alles wat begint met een `2` betekent 'succes', d.w.z. het ophalen is succesvol geweest. `200` betekent specifiek 'OK'.

- Om de werkelijke inhoud van de pagina te krijgen, kun je `r.text` gebruiken. Om deze inhoud op te slaan, zou je zoiets kunnen doen als:

    ```python
    import requests
url = "https://www.raspberrypi.org"
r = requests.get(url)
data = r.text
    ```

- Vaak hebben de gegevens die je van een website krijgt het **JSON** formaat. Je kunt dit eenvoudig converteren naar een Python-woordenboek met behulp van `r.json ()`, zoals hieronder weergegeven.

    ```python
    import requests
url = "https://www.raspberrypi.org"
r = requests.get(url)
data = r.json()
    ```
