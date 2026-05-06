# CityDB

Structured travel safety dataset. 100 cities, 30+ fields per entry, consulates in 10 languages.

## What's in it

Every city entry includes:

- **Consulates** — 10 languages (EN, DE, FR, HR, IT, ES, HI, AR, ZH, JA) with full address and phone
- **Emergency contacts** — hospital, police, pharmacy, dentist, vet
- **Airport** — IATA code, distance from centre, phone
- **Scams** — described with method and how to avoid
- **No-go zones** — with time-of-day context
- **Local rules** — laws tourists commonly break
- **Drinking water** — tap safety per city
- **Transport** — how to actually get around
- **Culture** — food, drink, attractions, famous companies, sport clubs
- **City info** — mayor, city hall, population, main square, railway station

## Cities covered

100 cities across Europe, Americas, Asia, Middle East, Africa and Oceania.

Europe: Vienna, Brussels, Bruges, Zurich, Lucerne, Geneva, Prague, Berlin, Frankfurt, Munich, Hamburg, Copenhagen, Madrid, Barcelona, Seville, Valencia, Palma, Granada, Helsinki, Paris, Nice, Lyon, London, Edinburgh, Athens, Thessaloniki, Zagreb, Dubrovnik, Split, Zadar, Šibenik, Pula, Rijeka, Novigrad, Pazin, Karlovac, Budapest, Dublin, Rome, Milan, Venice, Florence, Naples, Vilnius, Riga, Valletta, Amsterdam, Rotterdam, Oslo, Warsaw, Kraków, Lisbon, Porto, Faro, Bucharest, Belgrade, Novi Sad, Stockholm, Singapore, Ljubljana, Bratislava, Reykjavik, Sarajevo, Nicosia

Americas: New York, Los Angeles, Miami, Chicago, Las Vegas, Philadelphia, San Francisco, Toronto, Vancouver, Rio de Janeiro, Cancun, Mexico City, Buenos Aires

Asia: Tokyo, Osaka, Kyoto, Bangkok, Phuket, Seoul, Beijing, Shanghai, Bali, Hanoi, Delhi, Mumbai

Middle East / Africa: Dubai, Abu Dhabi, Doha, Marrakech, Cape Town

Oceania: Sydney, Melbourne, Auckland

## Schema

```js
"JP-tokyo": {
    country: "JP",
    consulate: {
        en: { name: "U.S. Embassy Tokyo", address: "1-10-5 Akasaka, Minato-ku", tel: "+81 3 3224 5000" },
        de: { name: "Deutsche Botschaft Tokio", address: "...", tel: "..." },
        // fr, hr, it, es, hi, ar, zh, ja
    },
    hospital: { name: "St. Luke's International Hospital", address: "...", tel: "..." },
    scams: [
        "Taxi overcharging from Narita: use only metered taxis from official ranks...",
    ],
    no_go: [ "Kabukicho after 02:00 — aggressive touts near adult venues" ],
    // ... 25 more fields
}
```

Key format: `ISO2-cityname` (e.g. `HR-dubrovnik`, `JP-tokyo`, `US-newyork`)

## License

MIT

## Use it in your project

```js
// Load citydb.js, then:
var data = CITY_DB["JP-tokyo"];
console.log(data.hospital.tel);      // emergency number
console.log(data.consulate.en.name); // English-speaking consulate
console.log(data.scams[0]);          // first scam to watch for
```

## Licensing for commercial use

Using this in a product? See the [pricing page](https://damc-979.github.io/citydb) or email **Mystudyglas@proton.me**

---

Data is curated by hand. Not scraped. Updated regularly.
