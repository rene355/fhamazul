# Starlink-subpagina

De website staat in `starlink/` en is bedoeld voor publicatie als:

`https://www.fhamazul.es/starlink/`

## Eenmalige inrichting

1. Maak een gratis Supabase-project aan.
2. Open in Supabase de SQL Editor en voer `starlink/supabase-setup.sql` uit.
3. Ga naar Authentication > Users en maak de beheerder `info@fhamazul.es` met een sterk wachtwoord aan.
4. Schakel openbare registratie uit via Authentication > Providers > Email > Allow new users to sign up.
5. Kopieer bij Settings > API Keys de Project URL en publishable key naar `starlink/config.js`.
6. Plaats de map `starlink` in de hoofdmap van de repository die de website publiceert.

De publishable key mag in een openbare website staan. De databasebeveiliging in het SQL-bestand zorgt ervoor dat bezoekers alleen mogen lezen. Gebruik nooit een secret- of service-role key in `config.js`.

## Werking

- Bezoekers zien de actuele geblokkeerde periodes zonder in te loggen.
- De kalender ververst bij het openen, bij terugkeren naar het tabblad en elke minuut.
- De beheerder logt onder de kalender in en kan periodes blokkeren of verwijderen.
- Bij een databasefout wordt reserveren uitgeschakeld, zodat geen onjuiste beschikbaarheid wordt getoond.
