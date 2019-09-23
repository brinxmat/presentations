# Nasjonalt vitenarkiv
## Hovedmål

“Nasjonalt vitenarkiv skal bidra til å realisere regjeringens mål om at alle norske vitenskapelige artikler som er finansiert av offentlige midler skal være åpent tilgjengelig innen 2024.” [1]

*Hovedmål fra rapporten er:*

  - Forskning i bred forstand, ikke bare hos institusjoner i UH-sektor
  - Det er snakk om et arkiv der forskere publiserer det de kan/skal arkivere
  - Arkiv her dekker også læringsressurs, data, og annet
  - Sørg for å øke gjenbruk av metadata fra arbeidsflyt som allerede eksisterer (fortrinnsvis hos institusjonen, videre nasjonalt)
  - Sørg for forenklende arbeidsflyt baserer seg i den grad mulig på automatisering
  - Forbedre nasjonal infrastruktur for oppgaver knyttet til arkivering av vitenskapelig arbeid
  
*Tiltakene:*

  - Etablering av infrastruktur som støtter innhenting og produksjon av metadata på nasjonalt plan og deling av disse
  
## Teknologier

I *Rapport fra utredning av nasjonalt vitenarkiv*, side 47: “[Prosjektgruppen anbefaler] at [NVA] bygges på en teknologisk plattform som er utviklet av Unit for å publisere digitale objekter, som f. eks. læringsobjekter og forskningsobjekter” Plattformen er basert på leading edge-teknologi og utnytter infrastruktur i skyen. Tjenestene DLR og BiRD kjører i dag på denne plattformen.”

I denne sammenhengen er "skyen" og "plattformen til DLR og BIRD" de viktige stikkordene.

Vi bruker AWS-stacken fullt ut, og baserer oss på *managed services* og teknologier som muliggjør kjapp utvikling og kontinuerlig urulling. Viktige lærdommer og erfaringer med teknologier fra tidligere AWS prosjekter taes med og vi skal få etablert en plattform som er tett integrert med AWS da dette har vist seg å være den mest fruktbar vei frem gitt forutsetningene vi har i Unit.

Den eksisterende plattformen som DLR og BIRD kjører på i dag er mikrotjenestebasert; flere deler av denne bearbeides slik at arkitekturen passer bedre inn i AWS. Arbeidet pågår allerede med å få realisert denne arkitekturen.

Ny frontend utvikles (i React) som dekker funksjonaliteten til NVA, DLR og BIRD tjenestene.

Gitt at vi tar sikte på kontinuerlig utrulling, ser vi selvfølgelig mye på testing og erfaring fra tidligere prosjekter viser at metodikken vi bruker fungerer godt, og at det er behov for videreutvikling av metodologien.

## Hvem jobber med dette?

Dette er et Unitprosjekt og folk fra flere avdelinger er involvert.

Utviklingsteamet er for tida hovedsakelig basert i Trondheim, men vi er får utviklere fra Oslo-kontoret inn fortløpende.

Det er hentet inn kompetanse både fra Oslo og ved innleie for å sikre at arbeidet med blant annet frontend pågår på en god måte.

Kompetansefolk med erfaring fra Cristin-miljøet er svært viktig i arbeidet og vi ser frem til samarbeidet her.

## Referanser
[1] Unit. 2019.  *Rapport fra utredning av nasjonalt vitenarkiv er ferdigstilt.* https://www.unit.no/aktuelt/rapport-fra-utredning-av-nasjonalt-vitenarkiv-er-ferdigstilt