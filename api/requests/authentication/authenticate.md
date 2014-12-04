---
layout: default
---

[Developer Hub](/) &raquo; [API](/api) &raquo; [Documentatie](/api/doc.html) &raquo; [Requests](/api/requests) &raquo; /authentication/authenticate

# /authentication/authenticate

Authenticeer jezelf, door het versturen van de gegenereerde response. Indien dit succesvol verloopt, kun je gedurende de lopende sessie de API-requests
aanroepen waarvoor authenticatie is vereist.

[Meer informatie over de authenticatieprocedure](/api/auth.html).

## Request

|**URL**          |http://www.uitzendbureau.nl/api/authentication/authenticate
|**HTTP-methode** |POST

## Parameters

|**Parameter** |**Type** |**Optioneel** |**Beschrijving**
|**sessionId** |String   |Nee           |De session identifier (hoofdlettergevoelig), die is verkregen bij het aanvragen van een challenge.
|**response**  |String   |Nee           |De response, zoals deze is gegenereerd door de client. Een beschrijving hiervan vind je [hier](/api/auth.html).

## Response

De response wordt aangeboden in JSON-formaat.

## Velden

|**Veld**                    |**Type** |**Optioneel** |**Beschrijving**
|**authenticationSucceeded** |Bool     |Nee           |Retourneert `true` indien de authenticatie succesvol is verlopen.

## Foutcodes

Eventuele fouten worden aangegeven in de vorm van HTTP status codes. Bij deze request kunnen de volgende foutcodes optreden:

|**400** |Controleer de meegestuurde parameters. Ben je `sessionId` of `response` vergeten, of zijn de waarden leeg?
|**401** |De authenticatie is mislukt.
|**500** |Er is een onverwachte fout opgetreden. Indien deze fout optreedt, neem dan contact op met ons via 0478-640204 of techniek@uitzendbureau.nl.

## Voorbeeldresponse

    {
        "authenticationSucceeded": true
    }