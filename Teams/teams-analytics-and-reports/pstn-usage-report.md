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
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Erfahren Sie, wie Sie im Microsoft Teams Admin Center den Bericht zur Verwendung des Teams PSTN verwenden, um einen Überblick über die Nutzung von Anrufen und Audiokonferenzen in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d870581b8921e39d50d0187120cf89067ac38819
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116863"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN-Nutzungsbericht

Der Nutzungsbericht des Teams PSTN (Public Switched Telephone Network) im Microsoft Teams Admin Center bietet Ihnen einen Überblick über die Aktivitäten von Anrufen und Audiokonferenzen in Ihrer Organisation. Sie können detaillierte Anrufaktivitäten für Anrufpläne anzeigen, wenn Sie Microsoft als Telefonieanbieter und für Direct Routing verwenden, wenn Sie Ihren eigenen Telefonnetzbetreiber verwenden.

Auf **der Registerkarte Anrufpläne** werden Informationen angezeigt, einschließlich der Anzahl der Minuten, die Benutzer für eingehende und ausgehende PSTN-Anrufe auf sich haben, sowie die Kosten für diese Anrufe. Auf **der Registerkarte Direktes Routing** werden Informationen einschließlich der SIP-Adresse und der Start- und Endzeiten von Anrufen angezeigt. Verwenden Sie die Informationen in diesem Bericht, um Einblicke in die PSTN-Nutzung in Ihrer Organisation zu erhalten und Ihnen dabei zu helfen, Geschäftsentscheidungen zu untersuchen, zu planen und zu treffen.

> [!NOTE]
> Wenn Sie über einen Anrufplan für Telstra oder Softbank verfügen, werden im Bericht pstN-Nutzung keine Anrufdetailsesätze dargestellt. Wenden Sie sich für Ihre Berichterstellungsanforderungen an Telstra oder Softbank. 

## <a name="view-the-pstn-usage-report"></a>Anzeigen des PstN-Nutzungsberichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf **Analytics & Berichte**  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **PSTN-Nutzungsbericht aus.**
2. Wählen **Sie unter** Datumsbereich einen vordefinierten Bereich von 7 oder 28 Tagen aus, oder legen Sie einen benutzerdefinierten Bereich fest, und wählen Sie dann Bericht ausführen **aus.**

## <a name="interpret-the-report"></a>Interpretieren des Berichts

### <a name="calling-plans"></a>Anrufpläne

[![Screenshot des Berichts zum PstN-Nutzungsbericht "Anrufpläne" im Admin Center](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Screenshot des PstN-Nutzungsberichts im Microsoft Teams Admin Center mit nummerierten Callouts")](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht kann nach Trends in den letzten 7 Tagen, 28 Tagen oder einem von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt werden. |
|**2**   |Jeder Bericht verfügt über ein Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse ist die Gesamtanzahl der Anrufe über den ausgewählten Zeitraum. <br>Zeigen Sie auf den Punkt an einem bestimmten Datum, um die Gesamtzahl der Aufrufe an diesem Datum zu sehen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Der Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Benutzername** ist der Anmeldename des Benutzers.</li><li>**Telefonnummer ist** die Rufnummer, die den Anruf für eingehende Anrufe oder die für ausgehende Anrufe gewählte Rufnummer erhalten hat.</li><li>**Der Anruftyp** ist die Frage, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PstN-Anruf und die Art des Anrufs handelt, z. B. einen Anruf, der von einem Benutzer oder einer Audiokonferenz platziert wurde. Zu den Anruftypen, die möglicherweise zu sehen sind, gehören:<br><br>**Anruftypen für Teams-Benutzer**<ul><li>**user_in** – Der Benutzer hat einen eingehenden PSTN-Anruf erhalten.</li><li>**user_out** – Der Benutzer hat einen ausgehenden PSTN-Anruf platziert</li><li>**user_out_conf** – Der Benutzer hat zwei oder mehr PSTN-Teilnehmer zu dem Anruf hinzugefügt, z. B. eine Drei-Wege-Telefonkonferenz.</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer übertragen</li><li>**user_out_forwarding** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**conf_in** – ein eingehender Anruf an die Audiokonferenzbrücke</li><li>**conf_out** – ein ausgehender Anruf von der Audiokonferenzbrücke in der Regel, um der Konferenz eine PSTN-Nummer hinzuzufügen</li></ul><br>**Anruftypen für Teams bots**<ul><li>**ucap_in** – ein eingehender PSTN-Anruf bei teams bot, z. B. automatische Telefonkonferenz oder Anrufwarteschleife</li><li>**ucap_out** – ein ausgehender PSTN-Anruf von einem Teams-Bot, z. B. automatischer Telefonkonferenz oder Anrufwarteschlange</li></ul><br><li>**Aufgerufen an** ist die gewählte Nummer.</li><li>**Im Land oder in der Region** wird das Land oder die Region gewählt.</li><li>**Von aufgerufen** ist die Nummer, die den Anruf platziert hat.</li><li>**Aus dem Land oder der Region** ist das Land oder die Region, aus dem der Anruf platziert wurde.</li><li>**"Gebühr"** ist der Betrag oder die Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird. </li><li>**Währung** ist der Währungstyp, der zum Berechnen der Kosten des Anrufs verwendet wird. </li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**In-/Ausland** teilt Ihnen anhand des Standorts des Benutzers mit, ob der Anruf im Inland (innerhalb eines Landes oder einer Region) oder international (außerhalb eines Landes oder einer Region) war.</li><li>**Anruf-ID** ist die ID für einen Anruf. Es ist ein Bezeichner für den Anruf, den Sie verwenden können, wenn Sie den Microsoft-Support anrufen.</li><li>**Der Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Rufnummer. </li><li>**Land oder Region** ist der Nutzungsstandort. </li> <li>**Konferenz-ID** ist die Konferenz-ID der Audiokonferenz. </li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den Lizenztypen, die möglicherweise zu sehen sind, gehören:<ul><li>**MCOEV oder MCOEV_VIRTUALUSER oder MCOEV_VIRTUALUSER_GOV** – Sprachanwendungen wie automatische Telefonkonferenz oder Anrufwarteschlangen</li><li>**FREECALL** – Bei einem technischen Problem, das uns an der Preisgestaltung eines Anrufs hindert, wird der Anruf kostenlos bereitgestellt und mit dieser Funktion angezeigt.</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** – Plan für Inlandsrufe (240 Minuten Anrufplan)</li><li>**MCOPSTN8** – Domestic Calling Plan 120 min pro Benutzer (nicht für Benutzer gepoolt wie die anderen Anrufpläne)</li><li>**MCOPSTN9** – Internationaler Anrufplan</li><li>**MCOPSTNCAP** – Common Area Phone</li><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung</li></ul></li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen **Sie Filtern** aus, um den Bericht nach Benutzername oder Anruftyp zu filtern. |
|**7**   |Wählen **Sie Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**8**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf Nach Excel** exportieren, und klicken Sie dann auf der Registerkarte **Downloads** auf **Herunterladen,** um den Bericht herunterzuladen, wenn er fertig ist.|

### <a name="direct-routing"></a>Direktes Routing

[![Screenshot des Direct Routing PSTN-Nutzungsberichts im Admin Center](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Screenshot des Direct Routing PSTN-Nutzungsberichts im Microsoft Teams Admin Center mit nummerierten Callouts")](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht kann für Trends der letzten 7 Tage oder 28 Tage angezeigt werden. |
|**2**   |Jeder Bericht verfügt über ein Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse ist die Gesamtanzahl der Anrufe über den ausgewählten Zeitraum.<br>Zeigen Sie auf den Punkt an einem bestimmten Datum, um die Gesamtzahl der Aufrufe an diesem Datum zu sehen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Der Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. Der Name kann auch der Name eines Bots sein, z. B. die Anrufwarteschlange oder cloudbasierte automatische Telefonzentrale. </li><li>**DIE SIP-Adresse** ist die SIP-Adresse des Benutzers oder bots, der den Anruf empfangen oder angenommen hat.</li><li>**Die Rufnummer des Anrufers** ist die Nummer des Benutzers oder bots, der den Anruf vorgenommen hat. </li><li>**Die Rufnummer des Anrufs** ist die Nummer des Benutzers oder bots, der den Anruf erhalten hat. Bei einem eingehenden Anruf bei einem Teams-Benutzer ist es der Teams-Benutzer, bei einem ausgehenden Anruf eines Teams-Benutzers der PSTN-Benutzer. </li><li>**Der Anruftyp** ist die Frage, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PstN-Anruf und die Art des Anrufs handelt, z. B. einen Anruf, der von einem Benutzer oder einer Audiokonferenz platziert wurde. Zu den Anruftypen, die möglicherweise zu sehen sind, gehören:<br><br>**Anruftypen für Teams-Benutzer**<ul><li>**dr_in** – Der Benutzer hat einen eingehenden PSTN-Anruf erhalten</li><li>**dr_out** – Der Benutzer hat einen ausgehenden PSTN-Anruf platziert</li><li>**dr_out_user_conf** – Der Benutzer hat dem Anruf einen PSTN-Teilnehmer hinzugefügt</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer übertragen</li><li>**dr_out_user_forwarding** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer übertragen</li><li>**dr_emergency_out** – der Benutzer hat einen Notruf abgerufen</li></ul><br>**Anruftypen für Teams bots**<ul><li>**dr_in_ucap** – ein eingehender PSTN-Anruf an einen Teams-Bot, z. B. automatische Telefonkonferenz oder Anrufwarteschleife</li><li>**dr_out_ucap** – ein ausgehender PSTN-Anruf von einem Teams-Bot, z. B. automatischer Telefonkonferenz oder Anrufwarteschlange</li></ul><br><li>**Aufgerufen an** ist die Nummer des Benutzers, der den Anruf empfangen hat.</li><li>**Startzeit (UTC)** ist der Zeitpunkt, zu dem der SIP-Proxy die endgültige Antwort (SIP-Nachricht "200 OK") vom SBC bei einem ausgehenden Anruf (Teams/Bot an einen PSTN-Benutzer) oder nachdem der SIP-Proxy die Einladung zum nächsten Hop im Teams-Back-End bei einem eingehenden Anruf (PSTN-Benutzer an einen Teams/Bot) gesendet hat. </li><li>**Einladungszeit (UTC)** ist der Zeitpunkt, zu dem die erste Einladung bei einem ausgehenden Anruf eines Teams-Benutzers oder Botanrufs an den SBC gesendet oder bei einem eingehenden Anruf bei einem Teams- oder Botanruf von der Komponente SIP-Proxy von Direct Routing vom SBC empfangen wurde.</li><li>**Die Fehlerzeit (UTC)** ist der Zeitpunkt, zu dem der Anruf fehlgeschlagen ist. Nur für fehlgeschlagene Anrufe. Der endgültige SIP-Code, der endgültige Microsoft-Untercode und der endgültige SIP-Ausdruck geben die Gründe für einen Fehler beim Aufruf an und können bei der Problembehandlung hilfreich sein. </li><li>**Endzeit (UTC) ist** die Uhrzeit, zu der der Anruf beendet wurde (nur für erfolgreiche Anrufe).</li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**Der Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Rufnummer. </li><li>**Die Medienumgehung** gibt an, ob der Trunk für die Medienumgehung aktiviert wurde. </li> <li>**SBC FQDN** ist der vollqualifizierte Domänenname (FQDN) des Session Border Controllers (SBC). </li><li>**Die Azure-Region für Medien** ist das Rechenzentrum, das als Medienpfad in einem Nichtumgehungsaufruf verwendet wurde. </li><li>**Azure region for Signaling** is the data center that was used for signaling for both bypass and non-bypass calls. </li><li>**Der Ereignistyp** ist der Ereignistyp des Aufrufs. Sie sehen Erfolg für erfolgreiche Anrufe und Versuch für fehlgeschlagene Anrufe. </li><li>**Letzter SIP-Code** ist der Code, mit dem der Aufruf beendet wurde.</li><li>**Der endgültige Microsoft-Untercode** ist ein Code, der bestimmte Aktionen angibt, die aufgetreten sind.</li><li>**Der letzte SIP-Ausdruck** ist die Beschreibung des SIP-Codes und des Microsoft-Untercodes.</li><li>**Korrelations-ID** ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Aufrufen des Microsoft-Support verwenden können.</li><li>**Die freigegebene Korrelations-ID** ist nur in der herunterladbaren CSV-Datei sichtbar und nicht im Portal vorhanden. Die freigegebene Korrelations-ID ist in mindestens zwei Aufrufen vorhanden, die miteinander verknüpft sind. Eine ausführliche Beschreibung finden Sie weiter unten.</li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen **Sie Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**7**   |Wählen **Sie Exportieren nach Excel** aus, um die Daten in einer durch Kommas getrennten Datei (CSV) für die Offlineanalyse herunterzuladen oder sie als Eingabe für Ihr Abrechnungssystem zu verwenden. |

#### <a name="callercallee-fields-considerations"></a>Überlegungen zu Anrufer-/Anruferfeldern

Je nach Anrufrichtung können die Namen des Anrufers oder des Anrufers nicht E164-Nummern enthalten.

Diese Felder können von den Kunden-SBC(en) stammen. Es gibt drei Formate, die der SBC an Direct Routing senden kann: E.164-Zahlen, Nicht-E.164-Zahlen und Zeichenfolgen.

- E.164-Telefonnummer von einem Benutzer mit einer E.164-Nummer an einen Benutzer, der auch über eine E.164-Nummer verfügt. 
- Rufen Sie über eine Nicht-E.164-Nummer an. Ein Benutzer aus einer PbX eines Drittanbieters, der mit Direct Routing verbunden ist, führt einen Anruf bei einem Teams-Benutzer aus. In diesem Fall kann es sich bei der Anrufernummer um eine beliebige Nicht-E.164-Nummer, z. B. +1001, handele. 
- Ein Spammer ruft an und zeigt keine Nummer, sondern nur einen Namen an, z. B. "Interner Umsatzdienst". Diese Zeichenfolge wird in den Berichten angezeigt.

#### <a name="about-shared-correlation-id"></a>Informationen zur freigegebenen Korrelations-ID

Die freigegebene Korrelations-ID ist nur in der exportierten Excel-Datei vorhanden, die Sie herunterladen, und gibt an, dass zwei oder mehr Aufrufe miteinander verknüpft sind. Im Folgenden werden die verschiedenen Szenarien und der Fall erläutert, wann die freigegebene Korrelations-ID vorhanden ist.

1.    PSTN Benutzer 1 auf einem PSTN-Endpunkt namens Teams User 1 on Teams Client, Anruftyp Dr_In, Korrelations-ID 57f28917-42k5-4c0c-9433-79734873f2ac, keine freigegebene Korrelations-ID.
2.    Teams User 1 on Teams client called PSTN User 1 on a PSTN endpoint, call type Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, no shared correlation ID.
3.    PSTN Benutzer 1 auf einem PSTN-Endpunkt namens "Teams User 2 on Teams Client", Anruftyp Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, freigegebene Korrelations-ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Vorhandener Anruf 3 mit Korrelations-ID "f45e9a25-9f94-46e7-a457-84f5940efde9". PSTN-Benutzer 1 in einem Anruf mit Teams User 2. Teams Benutzer 2 hat einen Anruf an Teams oder PSTN-Benutzer übertragen (blind oder konsultativ), Anruftyp Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, freigegebene Korrelations-ID f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportieren der Berichte
Klicken **Sie auf Nach Excel** exportieren, und klicken Sie dann auf der Registerkarte **Downloads** auf **Herunterladen,** um den Bericht herunterzuladen, wenn er fertig ist. Der Exportvorgang kann je nach Datenmenge einige Sekunden bis mehrere Minuten dauern.

Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Exportierte Dateien enthalten zusätzliche Felder, die im Onlinebericht nicht verfügbar sind. Diese können für die Problembehandlung und automatisierte Workflows verwendet werden.

 Sie erhalten eine ZIP-Datei mit dem Namen "**Calls.Export. `[identifier]` . zip**", mit dem Bezeichner als eindeutige ID für den Export, der zur Problembehandlung verwendet werden kann.

Wenn Sie über Anrufpläne und Direktes Routing verfügen, enthält die exportierte Datei möglicherweise Daten für beide Produkte. Die PstN-Nutzungsberichtdatei hat den Dateinamen "**PSTN.calls. `[UTC date]` . csv**" und Direct Routing "**DirectRouting.calls. `[UTC date]` csv".**

 Zusätzlich zu PSTN- und Direct Routing-Dateien enthält das Archiv die Datei "**parameters.js",** mit dem ausgewählten Exportzeitbereich und -funktionen.

Exportierte Dateien sind im CSV-Format (Comma Separated Values) mit [RFC 4180-Standard](https://tools.ietf.org/html/rfc4180) kompatibel. Die Dateien können in Excel oder jedem anderen standardkonformen Editor geöffnet werden, ohne dass Transformationen erforderlich sind.

Die erste Zeile der CSV enthält Spaltennamen. Alle Datumsangaben sind UTC und im [ISO 8601-Format.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Exported PSTN usage report

 Sie können Daten bis zu einem Jahr ab dem aktuellen Datum exportieren, es sei denn, länderspezifische Vorschriften verbieten die Aufbewahrung der Daten für 12 Monate.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Eindeutiger Anrufbezeichner |
> | 1 | Anruf-ID | `nvarchar(64)` | Anrufbezeichner. Nicht garantiert eindeutig |
> | 2 | Konferenz-ID | `nvarchar(64)` | ID der Audiokonferenz |
> | 3 | Benutzerspeicherort | `nvarchar(2)` | Ländercode des Benutzers, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Aufrufen der Benutzer-ID in Azure Active Directory.<br/> Diese und andere Benutzerinformationen sind für Botanruftypen null/leer (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (Anmeldename) in Azure Active Directory.<br/>Dies entspricht in der Regel der SIP-Adresse des Benutzers und kann mit der E-Mail-Adresse des Benutzers identisch sein. |
> | 6 | Anzeigename des Benutzers | `nvarchar(128)` | Anzeigename des Benutzers |
> | 7 | Anrufer-ID | `nvarchar(128)` | Nummer, die den Anruf für eingehende Anrufe erhalten hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde. [E.164-Format](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Anruftyp | `nvarchar(32)` | Ob es sich bei dem Anruf um einen ausgehenden oder eingehenden Festnetzanruf und die Art des Anrufs wie einen Anruf eines Benutzers oder eine Audiokonferenz |
> | 9 | Zahlentyp | `nvarchar(16)` | Telefonnummerntyp des Benutzers, z. B. gebührenfreier Dienst |
> | 10 | Inland/International | `nvarchar(16)` | Unabhängig davon, ob der Anruf im Inland (innerhalb eines Landes oder einer Region) oder international (außerhalb eines Landes oder einer Region) basierend auf dem Standort des Benutzers war |
> | 11 | Ziel wählt | `nvarchar(64)` | Land oder Region gewählt |
> | 12 | Zielnummer | `nvarchar(32)` | Im [E.164-Format gewählte Nummer](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Startzeit | `datetimeoffset` | Startzeit für Anrufe |
> | 14 | Endzeit | `datetimeoffset` | Anrufendezeit |
> | 15 | Dauer Sekunden | `int` | Wie lange der Anruf verbunden war |
> | 16 | Verbindungsgebühr | `numeric(16, 2)` | Verbindungsgebührenpreis |
> | 17 | Aufladen | `numeric(16, 2)` | Betrag oder Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird |
> | 18 | Währung | `nvarchar(3)` | Zum Berechnen der Kosten des Anrufs verwendete Währung ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funktion | `nvarchar(32)` | Die für den Anruf verwendete Lizenz |

### <a name="exported-direct-routing-usage-report"></a>Exported Direct Routing usage report

Sie können Daten bis zu fünf Monate (150 Tage) ab dem aktuellen Datum exportieren, es sei denn, länderspezifische Bestimmungen verbieten die Aufbewahrung der Daten für diesen Zeitraum.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | Eindeutiger Anrufbezeichner |
> | 1 | SIP-Adresse | `nvarchar(128)` | Die Adresse des Benutzers oder Bots, der den Anruf vorgenommen oder empfangen hat.<br/>Beachten Sie, dass dies tatsächlich UserPrincipalName (UPN, Anmeldename) in Azure Active Directory ist, was normalerweise mit der SIP-Adresse identisch ist. |
> | 2 | Display Name | `nvarchar(128)` | Der Name eines Benutzers oder eines Anrufbots (z. B. Anrufwarteschlange oder Automatische Telefonzentrale), wie im Microsoft 365 Admin Center festgelegt |
> | 3 | Benutzerland | `nvarchar(2)` | Ländercode des Benutzers, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Einladungszeitpunkt | `datetimeoffset` | Wenn der erste Einladungsaufruf ausgehend vom Benutzer oder Bot von Teams an den SBC gesendet wird oder beim Eingehenden an Teams oder Botanruf von der Komponente SIP-Proxy von Direct Routing vom SBC empfangen wird |
> | 5 | Startzeitpunkt | `datetimeoffset` | Zeitpunkt, zu dem der SIP-Proxy die endgültige Antwort (SIP-Nachricht "200 OK") vom SBC ausgehend (Teams/Bot an einen PSTN-Benutzer) oder nachdem der SIP-Proxy die Einladung zum nächsten Hop im Teams-Back-End bei eingehendem Anruf (PSTN-Benutzer an einen Teams/Bot) gesendet hat.<br/>Bei fehlgeschlagenen und nicht beantworteten Anrufen kann dies gleich Einladungs- oder Fehlerzeit sein. |
> | 6 | Fehlerzeit | `datetimeoffset` | Nur für fehlgeschlagene (nicht vollständig etablierte) Aufrufe vorhanden |
> | 7 | Endzeitpunkt | `datetimeoffset` | Nur für erfolgreiche (vollständig etablierte) Aufrufe vorhanden. Uhrzeit, zu der der Anruf beendet wurde |
> | 8 | Dauer (Sekunden) | `int` | Dauer des Anrufs |
> | 9 | Erfolg | `nvarchar(3)` | Ja/Nein. Erfolg oder Versuch |
> | 10 | Rufnummer | `nvarchar(32)` | Nummer des Benutzers oder Bots, der den Anruf gemacht hat. Bei eingehendem Anruf eines Teambenutzers wird es ein PSTN-Benutzer sein, beim ausgehenden Anruf des Teams-Benutzers wird die Teambenutzernummer angezeigt. |
> | 12 | Rufnummer | `nvarchar(32)` | Nummer des Benutzers oder Bots, der den Anruf erhalten hat. Bei eingehendem Anruf eines Teambenutzers ist es der Teams-Benutzer, bei ausgehenden Von Teams-Benutzeranrufen der PSTN-Benutzer. |
> | 13 | Anruftyp | `nvarchar(32)` | Anruftyp und -richtung |
> | 14 | Azure Region für Medien | `nvarchar(8)` | Das rechenzentrum, das für den Medienpfad beim Nichtumgehungsaufruf verwendet wird |
> | 15 | Azure-Region für Signalisierung | `nvarchar(8)` | Das Rechenzentrum, das für die Signalisierung sowohl für Umgehungs- als auch für Nichtumgehungsaufrufe verwendet wird |
> | 16 | Letzter SIP-Code | `int` | Der Code, mit dem der Aufruf beendet wurde, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Endgültiger Microsoft-Untercode | `int` | Zusätzlich zu den SIP-Codes verfügt Microsoft über eigene Untercodes, die auf das spezifische Problem hinweisen. |
> | 18 | Letzter SIP-Ausdruck | `nvarchar(256)` | Beschreibung des SIP-Codes und des Microsoft-Untercodes |
> | 19 | SBC FQDN | `nvarchar(64)` | Vollqualifizierter Domänenname des Sitzungsgrenzcontrollers |
> | 20 | Medienumgehung | `nvarchar(3)` | Ja/Nein. Gibt an, ob der Trunk für die Medienumgehung aktiviert wurde oder nicht |
> | 21 | Freigegebene Korrelations-ID | `uniqueidentifier` | Gibt an, dass zwei oder mehr Anrufe miteinander verknüpft sind |


## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)