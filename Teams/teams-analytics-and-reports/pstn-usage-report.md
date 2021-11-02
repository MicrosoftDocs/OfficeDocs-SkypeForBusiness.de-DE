---
title: Microsoft Teams PSTN-Nutzungsbericht
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Erfahren Sie, wie Sie den Bericht Teams PSTN-Nutzung im Microsoft Teams Admin Center verwenden, um einen Überblick über die Nutzung von Anrufen und Audiokonferenzen in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26c2f1af49c9e3ed7a5cc758200934fc9734d94f
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641185"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN-Nutzungsbericht

Der Teams PSTN(Public Switched Telephone Network)-Nutzungsbericht im Microsoft Teams Admin Center gibt Ihnen einen Überblick über die Anruf- und Audiokonferenzaktivitäten in Ihrer Organisation. Sie können detaillierte Anrufaktivitäten für Anrufpläne anzeigen, wenn Sie Microsoft als Telefonieanbieter und für Direct Routing verwenden, wenn Sie Ihren eigenen Netzbetreiber verwenden.

Auf **der Registerkarte Anrufpläne** werden Informationen angezeigt, einschließlich der Anzahl der Minuten, die Benutzer für ein- und ausgehende PSTN-Anrufe auf ausgegeben haben, sowie die Kosten dieser Anrufe. Auf **der Registerkarte Direktes Routing** werden Informationen angezeigt, einschließlich der SIP-Adresse sowie der Start- und Endzeiten von Anrufen. Verwenden Sie die Informationen in diesem Bericht, um Einblicke in die PSTN-Nutzung in Ihrer Organisation zu erhalten und Ihnen zu helfen, Geschäftsentscheidungen zu untersuchen, zu planen und zu treffen.

> [!NOTE]
> Wenn Sie über einen Anrufplan für Telstra oder Softbank verfügen, werden im PSTN-Nutzungsbericht keine Anrufdetailsetaildatensätze sehen. Wenden Sie sich für Ihre Meldungen an Telstra oder Softbank. 

## <a name="view-the-pstn-usage-report"></a>Anzeigen des PSTN-Nutzungsberichts

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Center auf **Analyseberichte**&  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **PSTN-Nutzungsbericht aus.**
2. Wählen **Sie unter Datumsbereich** einen vordefinierten Bereich von 7 oder 28 Tagen aus, oder legen Sie einen benutzerdefinierten Bereich fest, und wählen Sie **dann Bericht ausführen aus.**

## <a name="interpret-the-report"></a>Interpretieren des Berichts

### <a name="calling-plans"></a>Anrufpläne

   ![Screenshot des PSTN-Nutzungsberichts für Anrufpläne im Admin Center](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Screenshot des PSTN-Nutzungsberichts im Microsoft Teams Admin Center mit nummerierten Anrufen](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht werden die Trends über die letzten 7 Tage, 28 Tage oder einen von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt. |
|**2**   |Jeder Bericht hat das Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse gibt die Gesamtanzahl der Anrufe im ausgewählten Zeitraum an. <br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Gesamtzahl der Anrufe an diesem Datum zu sehen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist die Uhrzeit, zu der der Anruf begonnen hat.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Benutzername** ist der Anmeldename des Benutzers.</li><li>**Telefon Nummer ist** die Nummer, die den Anruf für eingehende Anrufe erhalten hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde.</li><li>**Anruftyp gibt** an, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PSTN-Anruf handelte und um welche Art von Anruf es sich handelte (z. B. von einem Benutzer oder einer Audiokonferenz aus einer Audiokonferenz). Folgende Arten von Anrufen werden möglicherweise verwendet:<br><br>**Teams von Benutzeranruftypen**<ul><li>**user_in** – Der Benutzer hat einen eingehenden PSTN-Anruf erhalten.</li><li>**user_out** – Der Benutzer hat einen ausgehenden PSTN-Anruf platziert.</li><li>**user_out_conf** – Der Benutzer hat zwei oder mehr PSTN-Teilnehmer zu dem Anruf hinzugefügt, z. B. eine dreiwegge Telefonkonferenz.</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer durchwiesen.</li><li>**user_out_forwarding** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**conf_in** – ein eingehender Anruf an die Audiokonferenzbrücke</li><li>**conf_out** – Ein ausgehender Anruf von der Audiokonferenzbrücke, um der Konferenz in der Regel eine PSTN-Nummer hinzuzufügen</li><li>**unassigned_in** – ein eingehender PSTN-Anruf über einen Anrufplan an eine nicht zugewiesene Nummer</li></ul><br>**Teams von Bots**<ul><li>**ucap_in** – ein eingehender PSTN-Anruf an einen Teams, z. B. eine automatische Telefonkonferenz oder eine Anrufwarteschleife</li><li>**ucap_out** – ein ausgehender PSTN-Anruf von einem Teams-Bot, z. B. einer automatischen Telefonkonferenz oder einer Anrufwarteschleife</li></ul><br><li>**Aufgerufen an** ist die nummerierte Nummer.</li><li>**In das Land bzw. die Region** wird das gewählte Land bzw. die Region gewählt.</li><li>**Aufgerufen von** ist die Nummer, die den Anruf platziert hat.</li><li>**Aus dem Land oder der Region** ist das Land bzw. die Region, aus dem bzw. der der Anruf anruft.</li><li>**Gebühren** ist der Betrag oder die Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird. </li><li>**Währung** ist der Währungstyp, der zum Berechnen der Kosten des Anrufs verwendet wird. </li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**Inlands-/Auslandsanrufe** gibt basierend auf dem Standort des Benutzers an, ob es sich um einen Inlandsanruf (in einem Land oder einer Region) oder einen Auslandsanruf (außerhalb eines Lands oder einer Region) handelt.</li><li>**Anruf-ID** ist die ID für einen Anruf. Es ist eine ID für den Anruf, den Sie verwenden können, wenn Sie den Microsoft-Support anrufen.</li><li>**Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Telefonnummer. </li><li>**Land oder Region** ist der Verwendungsstandort. </li> <li>**Konferenzkennung ist** die Konferenz-ID der Audiokonferenz. </li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Die folgenden Lizenztypen werden möglicherweise verwendet:<ul><li>**MCOEV oder MCOEV_VIRTUALUSER oder MCOEV_VIRTUALUSER_GOV** – Sprachanwendungen wie automatische Telefonkonferenz oder Anrufwarteschleifen</li><li>**FREECALL** – Im Fall eines technischen Problems, das verhindert, dass wir einen Anruf mit einer Preisgestaltung bepreisen können, wird der Anruf kostenlos bereitgestellt und mit dieser Funktion angezeigt.</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6–** Plan für Inlandsrufe (Anrufplan mit 240 Min.)</li><li>**MCOPSTN8** - Plan für Inland anrufe 120 Min. pro Benutzer (nicht über Benutzer gepoolt wie die anderen Anrufpläne)</li><li>**MCOPSTN9** – Plan für Auslandsrufe</li><li>**MCOPSTNCAP** – Gemeinsame Telefon</li><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETADD_DIALOUT_US** – Einwahlplan für Audiokonferenzen in den USA und Kanada</li><li>**MCOMEETADD_CN_GLOBAL** – Audiokonferenzen für Benutzer außerhalb von China</li><li>**MCOMEETADD_TATA** – Tata Communications Connections</li><li>**MCOMEETACPEA** – Audiokonferenzen mit Minutenzahl </li><li>**MCOMEETACPEA_GOV** – Audiokonferenzen mit Minuten pro Minute für Behörden</li></ul></li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen Sie **Filter** aus, um den Bericht nach Benutzernamen oder Anruftyp zu filtern. |
|**7**   |Wählen **Sie Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**8**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf In Excel** exportieren, und klicken  Sie dann auf der Registerkarte **Downloads** auf Herunterladen, um den Bericht herunterzuladen, wenn er bereit ist.|

### <a name="direct-routing"></a>Direct Routing

   ![Screenshot des Berichts "PSTN-Nutzungsbericht für Direct Routing" im Admin Center](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Screenshot des Berichts "PSTN-Nutzung mit Direct Routing" im Microsoft Teams Admin Center mit nummerierten Callouts](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht werden die Trends über die letzten 7 oder 28 Tage angezeigt. |
|**2**   |Jeder Bericht hat das Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse gibt die Gesamtanzahl der Anrufe im ausgewählten Zeitraum an.<br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Gesamtzahl der Anrufe an diesem Datum zu sehen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist die Uhrzeit, zu der der Anruf begonnen hat.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Seite "Einstellungen" des Benutzers im Microsoft Teams Admin Center zu wechseln. Der Name kann auch der Name eines Bots sein, z. B. die Anrufwarteschleife oder automatische Telefonzentrale. </li><li>**SIP-Adresse** ist die SIP-Adresse des Benutzers oder Bots, der den Anruf empfangen oder hergestellt hat.</li><li>**Rufnummer ist die** Nummer des Benutzers oder Bots, der den Anruf hergestellt hat. </li><li>**Rufnummer des Anrufs ist** die Nummer des Benutzers oder Bots, der den Anruf empfangen hat. Bei einem eingehenden Anruf an einen Teams-Benutzer ist es der Teams-Benutzer, bei einem ausgehenden Anruf von einem Teams-Benutzer der PSTN-Benutzer. </li><li>**Anruftyp gibt** an, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PSTN-Anruf handelte und um welche Art von Anruf es sich handelte (z. B. von einem Benutzer oder einer Audiokonferenz aus einer Audiokonferenz). Folgende Anruftypen werden möglicherweise verwendet:<br><br>**Teams von Benutzeranruftypen**<ul><li>**dr_in** – Der Benutzer hat einen eingehenden PSTN-Anruf erhalten</li><li>**dr_out** – Der Benutzer hat einen ausgehenden PSTN-Anruf platziert.</li><li>**dr_out_user_conf** – Der Benutzer hat einen PSTN-Teilnehmer zum Anruf hinzugefügt.</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer durchwiesen.</li><li>**dr_out_user_forwarding** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer durchwiesen.</li><li>**dr_emergency_out** – Der Benutzer hat einen Notruf abgerufen.</li><li>**dr_unassigned_in** – ein eingehender PSTN-Anruf über Direct Routing an eine nicht zugewiesene Nummer</li></ul><br>**Teams von Bots**<ul><li>**dr_in_ucap** – Ein eingehender PSTN-Anruf an einen Teams, z. B. eine automatische Telefonkonferenz oder eine Anrufwarteschleife</li><li>**dr_out_ucap** – ein ausgehender PSTN-Anruf von einem Teams, z. B. einer automatischen Telefonkonferenz oder einer Anrufwarteschleife</li></ul><br><li>**Aufgerufen an** ist die Nummer des Benutzers, der den Anruf empfangen hat.</li><li>Startzeit **(UTC)** ist die Uhrzeit, zu der der SIP-Proxy die endgültige Antwort (SIP-Nachricht "200 OK") von der SBC bei einem ausgehenden Anruf (Teams/Bot) an einen PSTN-Benutzer erhalten hat oder nachdem der SIP-Proxy die Einladung an den nächsten Hop im Teams-Back-End bei einem eingehenden Anruf (PSTN-Benutzer an einen Teams/Bot) gesendet hat. </li><li>Einladungszeit **(UTC)** ist die Zeit, zu der die erste Einladung zu einem ausgehenden Anruf von einem Teams-Benutzer oder -Botanruf bei der SBC oder zu einem eingehenden Anruf an einen Teams- oder Botanruf von der SIP-Proxykomponente von Direct Routing von SBC empfangen wurde.</li><li>**Die Fehlerzeit (UTC)** ist die Uhrzeit, zu der der Anruf fehlgeschlagen ist. Nur bei fehlgeschlagenen Aufrufen. Der endgültige SIP-Code, der endgültige Microsoft-Untercode und der endgültige SIP-Ausdruck geben die Gründe an, warum der Anruf fehlgeschlagen ist, und können bei der Problembehandlung helfen. </li><li>**Endzeit (UTC) ist** die Uhrzeit, zu der der Anruf beendet wurde (nur bei erfolgreichen Anrufen).</li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Telefonnummer. </li><li>**Die Medienumgehung** gibt an, ob der Trunk für die Medienumgehung aktiviert wurde. </li> <li>**SBC-FQDN** ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Session Border Controller (SBC). </li><li>**Azure-Region für Medien** ist das Rechenzentrum, das bei einem nicht umgehenden Aufruf als Medienpfad verwendet wurde. </li><li>**Die Azure-Region für Signalisierung** ist das Rechenzentrum, das sowohl für Umgehungs- als auch Nichtumgehungsaufrufe verwendet wurde. </li><li>**Der Ereignistyp** ist der Ereignistyp des -Aufrufs. Bei erfolgreichen Aufrufen wird Erfolg und Bei fehlgeschlagenen Aufrufen versuchen der Fehler (Attempt) sehen. </li><li>**Der endgültige SIP-Code** ist der Code, mit dem der Aufruf beendet wurde.</li><li>**Der endgültige Microsoft-Untercode** ist ein Code, der bestimmte aufgetretene Aktionen angibt.</li><li>**Der endgültige SIP-Ausdruck** ist die Beschreibung des SIP-Codes und des Microsoft-Untercodes.</li><li>**Die Korrelations-ID** ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Anruf beim Microsoft-Support verwenden können.</li><li>**Die freigegebene Korrelations-ID** ist nur in der herunterladbaren CSV-Datei sichtbar und nicht im Portal vorhanden. Die freigegebene Korrelations-ID ist in mindestens zwei verwandten Aufrufen vorhanden. Unten finden Sie eine detaillierte Beschreibung.</li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen **Sie Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**7**   |Wählen **Sie Exportieren nach Excel** aus, um die Daten zur Offlineanalyse in eine durch Kommas getrennte Datei (CSV) herunterzuladen oder sie als Eingabe für Ihr Abrechnungssystem zu verwenden. |

#### <a name="callercallee-fields-considerations"></a>Überlegungen zu Anrufer-/Anruferfeldern

Je nach Anrufrichtung können die Namen des Anrufers oder des Anrufers Nicht-E164-Nummern enthalten.

Diese Felder können von den Kunden-SBC(s) stammen. Es gibt drei Formate, die der SBC an Direct Routing senden kann: E.164-Zahlen, Nicht-E.164-Zahlen und Zeichenfolgen.

- E.164-Telefonnummer von einem Benutzer mit einer E.164-Nummer zu einem Benutzer, der auch über eine E.164-Nummer verfügt. 
- Anrufen von einer Nicht-E.164-Nummer Ein Benutzer von einer Drittanbieter-PbX, die mit Direct Routing verbunden ist, führt einen Anruf an einen Teams aus. In diesem Fall kann es sich bei der Anrufernummer um eine beliebige Nicht-E.164-Nummer (z. B. +1001) sein. 
- Ein Spammer ruft an und zeigt keine Nummer an, sondern nur einen Namen, z. B. "Interner Umsatzdienst". Diese Zeichenfolge wird in den Berichten angezeigt.

#### <a name="about-shared-correlation-id"></a>Informationen zur freigegebenen Korrelations-ID

Die freigegebene Korrelations-ID ist nur in der heruntergeladenen Excel vorhanden und gibt an, dass zwei oder mehr Aufrufe zusammenhängen. Im Folgenden werden die verschiedenen Szenarien sowie der Fall erläutert, wann die freigegebene Korrelations-ID vorhanden ist.

1.    PSTN-Benutzer 1 an einem PSTN-Endpunkt namens Teams Benutzer 1 im Teams-Client: Anruftyp Dr_In, Korrelations-ID 57f28917-42k5-4c0c-9433-79734873f2ac, keine freigegebene Korrelations-ID.
2.    Teams Benutzer 1 im Teams-Client namens PSTN Benutzer 1 auf einem PSTN-Endpunkt: Anruftyp Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, keine freigegebene Korrelations-ID.
3.    PSTN User 1 on a PSTN endpoint called a Teams User 2 on Teams client, Aufruftyp Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, freigegebene Korrelations-ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Vorhandener Aufruf 3 mit Korrelations-ID "f45e9a25-9f94-46e7-a457-84f5940efde9". PSTN User 1 in a call with Teams User 2. Teams Benutzer 2 hat einen Anruf an den Teams- oder PSTN-Benutzer durch übertragen (blind oder mit Durchsenden), Anruftyp Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, freigegebene Korrelations-ID f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportieren der Berichte
Klicken **Sie auf In Excel** exportieren, und klicken  Sie dann auf der Registerkarte **Downloads** auf Herunterladen, um den Bericht herunterzuladen, wenn er bereit ist. Der Exportvorgang kann je nach Menge der Daten zwischen einigen Sekunden und mehreren Minuten dauern.

Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Exportierte Dateien enthalten zusätzliche Felder, die im Onlinebericht nicht verfügbar sind. Diese können für die Problembehandlung und automatisierte Workflows verwendet werden.

 Sie erhalten eine ZIP-Datei mit dem Namen **"Calls.Export". `[identifier]`.zip**". Dabei ist der Bezeichner eine eindeutige ID für den Export, die für die Problembehandlung verwendet werden kann.

Wenn Sie sowohl über Anrufpläne als auch über Direct Routing verfügen, enthält die exportierte Datei möglicherweise Daten für beide Produkte. Die PstN-Nutzungsberichtsdatei hat den Dateinamen "**PSTN.calls. `[UTC date]`.csv**" und Direct Routing "**DirectRouting.calls. `[UTC date]`.csv**" aus.

 Zusätzlich zu PSTN- und Direct Routing-Dateien enthält das Archiv die Datei **"parameters.json"** mit dem ausgewählten Exportzeitbereich und den ausgewählten Funktionen.

Exportierte Dateien liegen im CSV-Format (Comma Separated Values) vor, das [RFC 4180-kompatibel](https://tools.ietf.org/html/rfc4180) ist. Die Dateien können in einem Excel oder einem anderen standardkonformen Editor geöffnet werden, ohne dass Transformationen erforderlich sind.

Die erste Zeile der CSV-Datei enthält Spaltennamen. Alle Datumsangaben sind UTC und im [ISO 8601-Format.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Exported PSTN usage report

 Sie können Daten bis zu einem Jahr ab dem aktuellen Datum exportieren, es sei denn, die landesspezifischen Bestimmungen untersagen die Aufbewahrung der Daten für 12 Monate.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Eindeutige Anruf-ID |
> | 1 | Anruf-ID | `nvarchar(64)` | Anruf-ID. Es ist nicht garantiert, dass sie eindeutig sind |
> | 2 | Konferenz-ID | `nvarchar(64)` | ID der Audiokonferenz |
> | 3 | Benutzerstandort | `nvarchar(2)` | Ländercode des Benutzers ISO [3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Aufrufen der Benutzer-ID in Azure Active Directory.<br/> Diese und andere Benutzerinformationen sind für Bot-Anruftypen NULL/leer (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (Anmeldename) in Azure Active Directory.<br/>Diese ist in der Regel mit der SIP-Adresse des Benutzers identisch und kann mit der E-Mail-Adresse des Benutzers identisch sein. |
> | 6 | Anzeigename des Benutzers | `nvarchar(128)` | Anzeigename des Benutzers |
> | 7 | Anrufer-ID | `nvarchar(128)` | Die Nummer, die den Anruf für eingehende Anrufe erhalten hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde. [E.164-Format](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Anruftyp | `nvarchar(32)` | Ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PSTN-Anruf und die Art des Anrufs wie einen anruf von einem Benutzer oder einer Audiokonferenz gab |
> | 9 | Zahlentyp | `nvarchar(16)` | Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Telefonnummer |
> | 10 | In- und Ausland | `nvarchar(16)` | Ob es sich um einen Inlandsanruf (innerhalb eines Landes oder einer Region) oder einen Auslandsanruf (außerhalb eines Lands oder einer Region) basierend auf dem Standort des Benutzers gab |
> | 11 | Ziel gewählt | `nvarchar(64)` | Gewähltes Land oder die gewählte Region |
> | 12 | Zielnummer | `nvarchar(32)` | Nummer im [E.164-Format](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Startzeit | `datetimeoffset` | Startzeit des Anrufs |
> | 14 | Endzeit | `datetimeoffset` | Endzeit für Anrufe |
> | 15 | Dauer Sekunden | `int` | Wie lange war die Verbindung zum Anruf? |
> | 16 | Verbindungsgebühr | `numeric(16, 2)` | Verbindungsgebührenpreis |
> | 17 | Aufladen | `numeric(16, 2)` | Betrag oder Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird |
> | 18 | Währung | `nvarchar(3)` | Zum Berechnen der Anrufkosten verwendete Währungstyp[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Funktion | `nvarchar(32)` | Die für den Anruf verwendete Lizenz |

### <a name="exported-direct-routing-usage-report"></a>Exported Direct Routing usage report

Sie können Daten bis zu fünf Monate (150 Tage) ab dem aktuellen Datum exportieren, es sei denn, die landesspezifischen Bestimmungen untersagen die Aufbewahrung der Daten für diesen Zeitraum.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | Korrelations-ID | `uniqueidentifier` | Eindeutige Anruf-ID |
> | 1 | SIP-Adresse | `nvarchar(128)` | Die Adresse des Benutzers oder Bots, der den Anruf hergestellt oder empfangen hat.<br/>Beachten Sie, dass es sich dabei eigentlich um den UserPrincipalName (UPN, Anmeldename) in Azure Active Directory handelt, der in der Regel mit der SIP-Adresse identisch ist. |
> | 2 | Display Name | `nvarchar(128)` | Der Name eines Benutzers oder eines Anrufbots (z. B. Anrufwarteschleife oder automatische Telefonzentrale) wie in Microsoft 365 Admin Center |
> | 3 | Land des Benutzers | `nvarchar(2)` | Ländercode des Benutzers ISO [3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Einladungszeitpunkt | `datetimeoffset` | Wenn der erste Einladungsaufruf vom Teams-Benutzer oder -Bot ausgehend oder bei einem eingehenden an Teams oder Botanruf von der SIP-Proxykomponente von Direct Routing vom SBC empfangen wurde |
> | 5 | Startzeitpunkt | `datetimeoffset` | Zeitpunkt, zu dem der SIP-Proxy die endgültige Antwort (SIP-Nachricht "200 OK") vom SBC beim ausgehenden Anruf (Teams/Bot an einen PSTN-Benutzer) oder nachdem der SIP-Proxy die Einladung zum nächsten Hop im Teams-Back-End bei einem eingehenden Anruf (PSTN-Benutzer an einen Teams/Bot) gesendet hat.<br/>Bei fehlgeschlagenen und nicht beantworteten Anrufen kann dies gleich dem Zeitpunkt der Einladung oder des Fehlschlags sein. |
> | 6 | Fehlerzeit | `datetimeoffset` | Nur für fehlgeschlagene (nicht vollständig aufgebaute) Aufrufe vorhanden |
> | 7 | Endzeitpunkt | `datetimeoffset` | Nur für erfolgreiche (vollständig etablierte) Aufrufe vorhanden. Uhrzeit, zu der der Anruf beendet wurde |
> | 8 | Dauer (Sekunden) | `int` | Dauer des Anrufs |
> | 9 | Erfolg | `nvarchar(3)` | Ja/Nein. Erfolg oder Versuch |
> | 10 | Rufnummer | `nvarchar(32)` | Die Nummer des Benutzers oder Bots, der den Anruf hergestellt hat. Beim eingehenden Anruf eines Teambenutzers ist es ein PSTN-Benutzer, bei einem ausgehenden Teams-Benutzeranruf ist dies die Teams Benutzernummer. |
> | 12 | Rufnummer des Anrufer | `nvarchar(32)` | Die Nummer des Benutzers oder Bots, der den Anruf empfangen hat. Beim eingehenden Anruf eines Teambenutzers ist es der Teams Benutzer, bei einem ausgehenden Anruf Teams Benutzer der PSTN-Benutzer. |
> | 13 | Anruftyp | `nvarchar(32)` | Anruftyp und -richtung |
> | 14 | Azure-Region für Medien | `nvarchar(8)` | Das rechenzentrum, das für den Medienpfad in einem Nichtumgehungsaufruf verwendet wird |
> | 15 | Azure-Region für Signalisierung | `nvarchar(8)` | Das Rechenzentrum, das für Umgehungs- und Nichtumgehungsaufrufe verwendet wird |
> | 16 | Endgültiger SIP-Code | `int` | Der Code, mit dem der Aufruf beendet wurde RFC [3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Endgültiger Microsoft-Untercode | `int` | Zusätzlich zu den SIP-Codes verfügt Microsoft über eigene Untercodes, die das spezifische Problem angeben. |
> | 18 | Endgültiger SIP-Satz | `nvarchar(256)` | Beschreibung des SIP-Codes und des Microsoft-Untercodes |
> | 19 | SBC-FQDN | `nvarchar(64)` | Vollqualifizierter Domänenname des Session Border Controllers |
> | 20 | Medienumgehung | `nvarchar(3)` | Ja/Nein. Gibt an, ob der Trunk für die Medienumgehung aktiviert wurde. |
> | 21 | Freigegebene Korrelations-ID | `uniqueidentifier` | Gibt an, dass zwei oder mehr Anrufe im Zusammenhang stehen |


## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
