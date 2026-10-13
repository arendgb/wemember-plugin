Bronkaartproef — echte stagingplugin
====================================

Gebruik Wemember staging (testing) versie 0.3.3 en meld aan met je stagingaccount.
Gebruik uitsluitend de stagingverbinding en werkruimte Noordlicht Operations — fictief testbedrijf. Productie is
geen vervanging als staging niet bereikbaar is. Alle voorbeelddata zijn verzonnen
en persoonlijk opgeslagen bij het testaccount. Andere testers kunnen ze zelf
importeren met dezelfde fixture; de proef deelt niets automatisch.

Installeren of bijwerken
  Claude Code: /plugin marketplace update wemember
               /plugin install wemember-staging@wemember
  Codex: kies Wemember staging (testing) in /plugins en werk de plugin bij.
  Begin daarna een nieuw gesprek en meld de stagingverbinding aan als nodig.
  Controleer in de plugininformatie dat versie 0.3.3 geladen is.
  Claude desktop met alleen een connector krijgt serverkaarten, maar de
  pluginregels/hookproef vereist de plugin. Noteer welke omgeving je test.

Data klaarzetten / protocol controleren (voor ontwikkelaars in wemember-ai/platform)
  node test/hosted/source-cards-qa.mjs --environment staging --workspace "Noordlicht Operations — fictief testbedrijf"
  De OAuth-aanmeldlink verschijnt. Meld aan en kies uitsluitend Noordlicht Operations — fictief testbedrijf.
  De script gebruikt de gewone MCP-tools; geen database, geheime sleutel of bypass.
  Tokens blijven uitsluitend in het geheugen van die procesrun.
  Bron-id's, versies en de echte paginalink staan in dist/source-card-qa/staging.json.
  Dezelfde voorbereiding kan met --environment sandbox --workspace "Noordlicht — sandbox".

Klaarzetten via de plugin (alternatief voor de script)
  Lees de volledige bestanden testing/source-cards/fixture.mjs en README.txt.
  Gebruik uitsluitend wemember-staging in werkruimte Noordlicht Operations — fictief testbedrijf. Importeer de drie
  sourceInputs uit de fixture persoonlijk met sources.upsert, sourceSystem
  wemember-source-card-qa en relativePath <externalId>.md. Prefix externalId met je geverifieerde
  actor.userId uit workspace.brief (bijvoorbeeld <actor>:onboarding). Zoek de persoonlijke
  pagina [Bronkaartproef] Jouw eerste werkdag eerst op; publiceer pageHtml alleen
  als die ontbreekt. Publiceer of deel niets in productie. Bevestig titels en
  echte links, geen broncode.

Testen
  De twaalf prompts en verwachtingen staan in fixture.mjs (scenarios), en na
  voorbereiding leesbaar in dist/source-card-qa/staging.txt. Voer de serie in beide
  hosts uit; voor Alleen op verzoek -> Bron toch expliciet vragen -> Gevraagde
  pagina -> Suggesties weer aan gebruik je hetzelfde gesprek. Begin andere
  scenario's in een nieuw gesprek. Test ook smalle breedte en donkere weergave.

De bronkaart met BEIDE links
  Toon met de stagingverbinding in Noordlicht één sources.view-kaart, met de id
  en versie van Starten bij Noordlicht en pageId van Jouw eerste werkdag uit het
  voorbereidingsrapport. Gebruik de echte toolresultaten; geen eigen artifact.

Versiescenario — uitsluitend deze eigen testbron veranderen
  Werk mijn persoonlijke bron [Bronkaartproef] Starten bij Noordlicht bij met
  sources.upsert in de stagingwerkruimte Noordlicht Operations — fictief testbedrijf. Gebruik dezelfde persoonsgebonden provenance
  uit het voorbereidingsrapport en de exacte huidige expectedVersion. Behoud de volledige
  brontekst en vervang alleen 09:00 door 09:30. Toon de nieuwe versie, maar
  vernieuw de eerder geopende kaart niet. Verander geen andere bron.
  Voor een herhaling kan de voorbereiding de originele fixture herstellen.

Wat dit bewijst
  De hosted script controleert OAuth, toolbeschikbaarheid, exacte versie,
  volledige readerchunks, echte links, vertrouwde UI-resources en tekstfallback.
  Hij simuleert GEEN native host. Aftekenen van automatisch tonen, voorkeurbericht,
  layout en klikken in Claude/Codex vereist de bovenstaande echte desktopproef.
  Noteer host + pluginversie + datum + scenario + feitelijk resultaat/foutmelding.
  Gebruik uitsluitend de sandbox/staging Noordlicht-testdata.
