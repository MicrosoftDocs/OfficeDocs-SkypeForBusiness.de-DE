---
title: Bericht zur Microsoft Teams -PSTN-Verwendung
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
description: Erfahren Sie, wie Sie den Bericht zur Verwendung des Teams PSTN im Microsoft Teams Admin Center verwenden, um einen Überblick über die Nutzung von Anrufen und Audiokonferenzen in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc2b1ae0b6df29e29a55152dbafb9b76ae31e973
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809295"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Bericht zur Microsoft Teams -PSTN-Verwendung

Der Bericht "PstN-Nutzung von Teams" im Microsoft Teams Admin Center gibt Ihnen einen Überblick über die Anruf- und Audiokonferenzaktivitäten in Ihrer Organisation. Sie können detaillierte Anrufaktivitäten für Anrufpläne anzeigen, wenn Sie Microsoft als Telefonieanbieter und für Direct Routing verwenden, wenn Sie Ihren eigenen Telefonieanbieter verwenden.

Auf **der Registerkarte "Anrufpläne"** werden Informationen angezeigt, einschließlich der Anzahl der Minuten, die Benutzer für ein- und ausgehende Anrufe über das Festnetz verbracht haben, sowie die Kosten für diese Anrufe. Auf **der Registerkarte "Direktes Routing"** werden Informationen einschließlich der SIP-Adresse und der Start- und Endzeiten von Anrufen angezeigt. Verwenden Sie die Informationen in diesem Bericht, um Einblicke in die Nutzung des Festnetz in Ihrer Organisation zu erhalten und Ihnen dabei zu helfen, Geschäftsentscheidungen zu untersuchen, zu planen und zu treffen.

> [!NOTE]
> Wenn Sie über einen Anrufplan für Telstra oder Softbank verfügen, werden im Bericht zur Verwendung des Festnetznetz keine Anrufdetailsetaildatensätze sehen. Wenden Sie sich für Ihre Berichterstellungsanforderungen an Telstra oder Softbank. 

## <a name="view-the-pstn-usage-report"></a>Anzeigen des Berichts "PSTN-Verwendung"

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf "Analysefunktionen&   >  **Verwendungsberichte.** Wählen Sie **auf der Registerkarte "Berichte anzeigen"** unter **"Bericht"** die Option **"PSTN-Nutzungsbericht" aus.**
2. Wählen **Sie unter "Datumsbereich"** einen vordefinierten Bereich von 7 oder 28 Tagen aus, oder legen Sie einen benutzerdefinierten Bereich fest, und wählen Sie dann "Bericht **ausführen" aus.**

## <a name="interpret-the-report"></a>Interpretieren des Berichts

### <a name="calling-plans"></a>Anrufpläne

[![Screenshot des Berichts "PstN-Nutzungsbericht](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Screenshot des Berichts "PSTN-Nutzung" im Microsoft Teams Admin Center mit nummerierten Callouts") für Anrufpläne" im Admin Center](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht werden die Trends über die letzten 7 Tage, 28 Tage oder einen von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt. |
|**2**   |Jeder Bericht hat ein Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse gibt die Gesamtzahl der Anrufe im ausgewählten Zeitraum an. <br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Gesamtzahl der Anrufe an diesem Datum zu sehen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Der Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf begonnen hat.</li><li>**Der Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**"Benutzername"** ist der Anmeldename des Benutzers.</li><li>**Die Telefonnummer ist** die Nummer, die den Anruf für eingehende Anrufe erhalten hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde.</li><li>**Die Anrufart** gibt an, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PstN-Anruf handelt, und um die Art des Anrufs, z. B. den Anruf eines Benutzers oder eine Audiokonferenz. Die folgenden Anruftypen werden möglicherweise verwendet:<br><br>**Anruftypen für Benutzer in Teams**<ul><li>**user_in** – Der Benutzer hat einen eingehenden Anruf über das Festnetz erhalten.</li><li>**user_out** – Der Benutzer hat einen ausgehenden Festnetzanruf platziert.</li><li>**user_out_conf** – Der Benutzer hat dem Anruf zwei oder mehr Teilnehmer hinzugefügt, z. B. eine dreiwegvernetzte Telefonkonferenz.</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine Festnetznummer durch übertragen.</li><li>**user_out_forwarding** – Der Benutzer hat den Anruf an eine Festnetznummer weitergeleitet.</li><li>**conf_in** – ein eingehender Anruf an die Audiokonferenzbrücke</li><li>**conf_out** - ausgehender Anruf von der Audiokonferenzbrücke, um der Konferenz in der Regel eine Rufnummer hinzuzufügen</li></ul><br>**Anruftypen für Teams-Bots**<ul><li>**ucap_in** – ein eingehender PSTN-Anruf an einen Teams-Bot, z. B. automatische Telefonisten oder Anrufwarteschleife</li><li>**ucap_out** – ein ausgehender PSTN-Anruf von einem Teams-Bot, z. B. einer automatischen Telefonwarteschlange oder Anrufwarteschleife</li></ul><br><li>**"Aufgerufen an"** ist die gewählte Nummer.</li><li>**In das Land bzw.** die Region ist das Land bzw. die Region gewählt.</li><li>**"Von"** ist die Nummer, von der der Anruf abgerufen wurde.</li><li>**Aus dem Land oder der Region** ist das Land oder die Region, aus dem bzw. der der Anruf anruft.</li><li>**Die** Gebühr ist der Betrag oder die Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird. </li><li>**Die** Währung ist der Typ der Währung, mit der die Kosten des Anrufs berechnet werden. </li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**Inlands-/Auslandsanrufe** lassen sich je nach Standort des Benutzers in einem Inland (in einem Land oder einer Region) oder international (außerhalb eines Landes oder einer Region) anrufen.</li><li>**Anruf-ID** ist die ID für einen Anruf. Dies ist eine ID für den Anruf, den Sie verwenden können, wenn Sie den Microsoft Support anrufen.</li><li>**Der Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Telefonnummer. </li><li>**Das Land oder die Region** ist der Verwendungsstandort. </li> <li>**Die Konferenz-ID** ist die Konferenz-ID der Audiokonferenz. </li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den Lizenztypen, die möglicherweise verwendet werden, gehören:<ul><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOEV oder MCOEV_VIRTUALUSER** – Sprachanwendungen wie automatische Telefonwarteschlange oder Anrufwarteschleifen</li><li>**FREECALL** – Im Fall eines technischen Problems, das uns an der Preisgestaltung eines Anrufs hindert, wird der Anruf kostenlos bereitgestellt und mit dieser Funktion angezeigt.</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** – Plan für Inlandsrufe (Anrufplan für 240 Minuten)</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung</li></ul></li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen Sie **"Filter"** aus, um den Bericht nach Benutzername oder Anruftyp zu filtern. |
|**7**   |Wählen **Sie "Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**8**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf "Nach Excel exportieren",** und klicken Sie dann auf der Registerkarte **"Downloads"** auf "Herunterladen", um den Bericht herunterzuladen, sobald er bereit ist. |

### <a name="direct-routing"></a>Direktes Routing

[![Screenshot des Berichts "Direct Routing PSTN-Nutzung" im Admin Center](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Screenshot des Direct Routing PSTN-Nutzungsberichts im Microsoft Teams Admin Center mit nummerierten Callouts")](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht werden die Trends über die letzten 7 Tage oder 28 Tage angezeigt. |
|**2**   |Jeder Bericht hat ein Datum, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse gibt die Gesamtzahl der Anrufe im ausgewählten Zeitraum an.<br>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Gesamtzahl der Anrufe an diesem Datum zu sehen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Der Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf begonnen hat.</li><li>**Der Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. Der Name kann auch der Name eines Bots sein, z. B. die Anrufwarteschleife oder automatische Telefonzentrale. </li><li>**Die SIP-Adresse** ist die SIP-Adresse des Benutzers oder Bots, der den Anruf empfangen oder hergestellt hat.</li><li>**Die Rufnummer des** Benutzers oder Bots, der den Anruf hergestellt hat. </li><li>**Die Rufnummer des Anrufs** ist die Nummer des Benutzers oder Bots, der den Anruf empfangen hat. Bei einem eingehenden Anruf an einen Teambenutzer ist dies der Teams-Benutzer, bei einem ausgehenden Anruf eines Teams-Benutzers ist dies der PSTN-Benutzer. </li><li>**Die Anrufart** gibt an, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PstN-Anruf handelt, und um die Art des Anrufs, z. B. den Anruf eines Benutzers oder eine Audiokonferenz. Die folgenden Anruftypen werden möglicherweise verwendet:<br><br>**Anruftypen für Benutzer in Teams**<ul><li>**dr_in** – Der Benutzer hat einen eingehenden Anruf über das Festnetz erhalten</li><li>**dr_out** – Der Benutzer hat einen ausgehenden Festnetzanruf platziert.</li><li>**dr_out_user_conf** – Der Benutzer hat einen Teilnehmer im öffentlichen Telefonnetz zum Anruf hinzugefügt.</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine Festnetznummer durch übertragen.</li><li>**dr_out_user_forwarding** – Der Benutzer hat den Anruf an eine Festnetznummer weitergeleitet.</li><li>**dr_out_user_transfer** – Der Benutzer hat den Anruf an eine Rufnummer über das Festnetz übertragen.</li><li>**dr_emergency_out** – Der Benutzer hat einen Notruf abgerufen.</li></ul><br>**Anruftypen für Teams-Bots**<ul><li>**dr_in_ucap** – ein eingehender PSTN-Anruf an einen Teams-Bot, z. B. eine automatische Telefonwarteschlange oder eine Anrufwarteschleife</li><li>**dr_out_ucap** – ein ausgehender PSTN-Anruf von einem Teams-Bot, z. B. einer automatischen Telefonwarteschlange oder einer Anrufwarteschleife</li></ul><br><li>**"Angerufen"** ist die Nummer des Benutzers, der den Anruf empfangen hat.</li><li>Die Startzeit **(UTC)** ist die Uhrzeit, zu der der -SIP-Proxy bei einem ausgehenden Anruf (Teams/Bot an einen PSTN-Benutzer) oder nach dem Senden der Einladung zum nächsten Hop im Teams-Back-End bei einem eingehenden Anruf (PSTN-Benutzer an einen Teams/Bot) die letzte Antwort vom SBC erhalten hat (SIP-Nachricht "200 OK"). </li><li>Die Einladungszeit **(UTC)** ist die Zeit, zu der die erste Einladung bei einem ausgehenden Anruf von einem Teams-Benutzer oder -Botanruf an den SBC oder bei einem eingehenden Anruf an einen Teams- oder Botanruf von der SIP-Proxykomponente von Direct Routing von SBC empfangen wurde.</li><li>**Die Fehlerzeit (UTC)** ist die Uhrzeit, zu der der Anruf fehlgeschlagen ist. Nur für fehlgeschlagene Anrufe. Der endgültige SIP-Code, der endgültige Microsoft-Untercode und der endgültige SIP-Satz geben die Gründe an, warum der Anruf fehlgeschlagen ist, und können bei der Problembehandlung helfen. </li><li>**Die Endzeit (UTC)** ist die Uhrzeit, zu der der Anruf beendet wurde (nur bei erfolgreichen Anrufen).</li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**Der Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Telefonnummer. </li><li>**Die Medienumgehung** gibt an, ob der Trunk für die Medienumgehung aktiviert wurde. </li> <li>**SBC-FQDN** ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Session Border Controllers (SBC). </li><li>**Die Region Azure für Medien** ist das Rechenzentrum, das in einem Nichtumgehungsaufruf als Medienpfad verwendet wurde. </li><li>**Die Region Azure für Signalisierung** ist das Rechenzentrum, das zum Signalisieren von Umgehungs- und Nicht-Umgehungsaufrufen verwendet wurde. </li><li>**Der Ereignistyp** ist der Ereignistyp des Aufrufs. Bei erfolgreichen Aufrufen und bei fehlgeschlagenen Aufrufen wird "Versuch" als "Erfolg" bezeichnet. </li><li>**Der endgültige SIP-Code** ist der Code, mit dem der Anruf beendet wurde.</li><li>**Der endgültige Microsoft-Untercode** ist ein Code, der bestimmte aufgetretene Aktionen angibt.</li><li>**Der letzte SIP-Begriff** ist die Beschreibung des SIP-Codes und des Microsoft-Untercodes.</li><li>**Die Korrelations-ID** ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Anruf beim Microsoft Support verwenden können.</li><li>**Die freigegebene Korrelations-ID** ist nur in der herunterladbaren CSV-Datei sichtbar und nicht im Portal vorhanden. Die freigegebene Korrelations-ID ist in mindestens zwei verwandten Aufrufen vorhanden. Bitte lesen Sie unten eine detaillierte Beschreibung.</li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen **Sie "Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**7**   |Wählen **Sie "Nach Excel exportieren"** aus, um die Daten in einer durch Kommas getrennten Datei (CSV) für die Offlineanalyse herunterzuladen oder sie als Eingabe für Ihr Abrechnungssystem zu verwenden. |

#### <a name="callercallee-fields-considerations"></a>Überlegungen zu Anrufer-/Anruferfeldern

Je nach Anrufrichtung können die Anrufer- oder Anrufernamen Nicht-E164-Nummern enthalten.

Diese Felder können von den Kunden-SBC(s) stammen. Es gibt drei Formate, die der SBC an Direct Routing senden kann: E.164-Zahlen, Nicht-E.164-Zahlen und Zeichenfolgen.

- E.164-Telefonnummer von einem Benutzer, der über eine E.164-Nummer verfügt, zu einem Benutzer, der auch über eine E.164-Nummer verfügt. 
- Anruf von einer Nicht-E.164-Nummer Ein Benutzer von einer Drittanbieter-PBX, die mit Direct Routing verbunden ist, führt einen Anruf an einen Teams-Benutzer. In diesem Fall kann es sich bei der Anrufernummer um eine beliebige Nicht-E.164-Nummer(z. B. +1001) um eine Nummer ohne E.164-Nummer( 
- Ein Spammer ruft an und zeigt keine Nummer an, sondern nur einen Namen, z. B. "Interner Umsatzdienst". Diese Zeichenfolge wird in den Berichten angezeigt.

#### <a name="about-shared-correlation-id"></a>Informationen zur freigegebenen Korrelations-ID

Die freigegebene Korrelations-ID ist nur in der exportierten Excel-Datei vorhanden, die Sie herunterladen, und gibt an, dass zwei oder mehr Aufrufe im Zusammenhang stehen. Im Folgenden werden die verschiedenen Szenarien und der Fall erläutert, wann die freigegebene Korrelations-ID vorhanden ist.

1.    PSTN User 1 an einem PSTN-Endpunkt mit namen "Teams User 1" im Teams-Client, Anruftyp Dr_In, Korrelations-ID 57f28917-42k5-4c0c-9433-79734873f2ac, keine freigegebene Korrelations-ID.
2.    Teams User 1 im Teamclient namens PSTN User 1 auf einem PSTN-Endpunkt, Anruftyp Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, keine freigegebene Korrelations-ID.
3.    PSTN User 1 an einem PSTN-Endpunkt, der im Teamclient als Benutzer 2 von Teams bezeichnet wird, Anruftyp Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, freigegebene Korrelations-ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Vorhandener Aufruf 3 mit Korrelations-ID "f45e9a25-9f94-46e7-a457-84f5940efde9". PSTN User 1 in a call with Teams User 2. Teams User 2 hat einen Anruf an Teams oder einen Benutzer im öffentlichen Telefonnetz (blind oder durch eine Kennung) übertragen, den Anruftyp Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, freigegebene Korrelations-ID f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportieren der Berichte
Klicken **Sie auf "Nach Excel exportieren",** und klicken Sie dann auf der Registerkarte **"Downloads"** auf "Herunterladen", um den Bericht herunterzuladen, sobald er bereit ist.  Der Exportvorgang kann je nach Menge der Daten zwischen einigen Sekunden und mehreren Minuten dauern.

Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Exportierte Dateien enthalten zusätzliche Felder, die im Onlinebericht nicht verfügbar sind. Diese können für die Problembehandlung und automatisierte Workflows verwendet werden.

 Sie erhalten eine ZIP-Datei namens **"Calls.Export. `[identifier]` . zip**", mit dem Bezeichner als eindeutige ID für den Export, der zur Problembehandlung verwendet werden kann.

Wenn Sie sowohl über Anrufpläne als auch über direktes Routing verfügen, enthält die exportierte Datei möglicherweise Daten für beide Produkte. Die Berichtsdatei für die PstN-Verwendung hat den Dateinamen **"PSTN.calls". `[UTC date]` csv**" und Direct Routing "**DirectRouting.calls. `[UTC date]` ".**

 Zusätzlich zu PSTN- und Direct-Routing-Dateien enthält das Archiv die Datei **"parameters.json"** mit dem ausgewählten Exportzeitbereich und den ausgewählten Funktionen.

Exportierte Dateien liegen im CSV-Format (Comma Separated Values) vor, das [rfc 4180-kompatibel](https://tools.ietf.org/html/rfc4180) ist. Die Dateien können in Excel oder einem anderen standardkonformen Editor geöffnet werden, ohne dass Transformationen erforderlich sind.

Die erste Zeile der CSV enthält Spaltennamen. Alle Datumsangaben sind UTC und im [ISO 8601-Format.](https://en.wikipedia.org/wiki/ISO_8601)

### <a name="exported-pstn-usage-report"></a>Exported PSTN usage report

 Sie können Daten bis zu einem Jahr ab dem aktuellen Datum exportieren, es sei denn, die landesspezifischen Vorschriften untersagen die Aufbewahrung der Daten für 12 Monate.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Eindeutige Anruf-ID |
> | 1 | Anruf-ID | `nvarchar(64)` | Anrufbezeichner. Nicht garantiert eindeutig |
> | 2 | Konferenz-ID | `nvarchar(64)` | ID der Audiokonferenz |
> | 3 | Benutzerstandort | `nvarchar(2)` | Ländercode des Benutzers, [ISO 3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Aufrufen der Benutzer-ID in Azure Active Directory.<br/> Diese und andere Benutzerinformationen sind null/leer für Bot-Anruftypen (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | "UserPrincipalName" (Anmeldename) in Azure Active Directory.<br/>Dies entspricht normalerweise der SIP-Adresse des Benutzers und kann mit der E-Mail-Adresse des Benutzers identisch sein. |
> | 6 | Anzeigename des Benutzers | `nvarchar(128)` | Anzeigename des Benutzers |
> | 7 | Anrufer-ID | `nvarchar(128)` | Die Nummer, die den Anruf für eingehende Anrufe erhalten hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde. [E.164-Format](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Anruftyp | `nvarchar(32)` | Ob es sich bei dem Anruf um einen ausgehenden oder eingehenden Festnetzanruf und den Anruftyp (z. B. einen Anruf eines Benutzers oder eine Audiokonferenz) ging |
> | 9 | Zahlentyp | `nvarchar(16)` | Telefonnummerntyp des Benutzers, z. B. eine gebührenfreie Telefonnummer |
> | 10 | In- und Ausland | `nvarchar(16)` | Ob es sich um einen Inlandsanruf (innerhalb eines Landes oder einer Region) oder einen internationalen Anruf (außerhalb eines Landes oder einer Region) basierend auf dem Standort des Benutzers gab |
> | 11 | Ziel gewählt | `nvarchar(64)` | Gewähltes Land bzw. eine gewählte Region |
> | 12 | Zielnummer | `nvarchar(32)` | Nummer, die im [E.164-Format gewählt](https://en.wikipedia.org/wiki/E.164) wurde |
> | 13 | Startzeit | `datetimeoffset` | Startzeit des Anrufs |
> | 14 | Endzeit | `datetimeoffset` | Anrufendezeit |
> | 15 | Dauer (Sekunden) | `int` | Wie lange war der Anruf verbunden? |
> | 16 | Verbindungsgebühr | `numeric(16, 2)` | Verbindungsgebührenpreis |
> | 17 | Aufladen | `numeric(16, 2)` | Betrag oder Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird |
> | 18 | Währung | `nvarchar(3)` | Zum Berechnen der Anrufkosten verwendete Währungstyp[(ISO 4217)](https://en.wikipedia.org/wiki/ISO_4217) |
> | 19 | Funktion | `nvarchar(32)` | Die für den Anruf verwendete Lizenz |

### <a name="exported-direct-routing-usage-report"></a>Bericht zur Verwendung des direkten Routings exportiert

Sie können Daten bis zu fünf Monate (150 Tage) ab dem aktuellen Datum exportieren, es sei denn, länderspezifische Vorschriften untersagen die Aufbewahrung der Daten für diesen Zeitraum.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | Korrelations-ID | `uniqueidentifier` | Eindeutige Anruf-ID |
> | 1 | SIP Address | `nvarchar(128)` | Die Adresse des Benutzers oder Bots, der den Anruf hergestellt oder empfangen hat.<br/>Beachten Sie, dass dies tatsächlich "UserPrincipalName"(UPN, Anmeldename) in Azure Active Directory ist, was normalerweise mit der ADRESSE des SIP identisch ist. |
> | 2 | Display Name | `nvarchar(128)` | Der Name eines Benutzers oder eines Anrufbots (z. B. Anrufwarteschleife oder automatische Telefonzentrale), wie im Microsoft 365 Admin Center festgelegt |
> | 3 | Land des Benutzers | `nvarchar(2)` | Ländercode des Benutzers, [ISO 3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | Einladungszeitpunkt | `datetimeoffset` | Wenn die erste Einladung, die ausgehend von Einem Teams-Benutzer oder -Bot gesendet wird, beim SBC anruft oder bei einem eingehenden Anruf an Teams oder einem Botanruf von der KOMPONENTE "SIP-Proxy" des direkten Routings vom SBC empfangen wird |
> | 5 | Startzeitpunkt | `datetimeoffset` | Zeitpunkt, zu dem der SIP-Proxy die endgültige Antwort (SIP-Nachricht "200 OK") vom SBC auf ausgehend (Teams/Bot an einen PSTN-Benutzer) oder nach dem Senden der Einladung zum nächsten Hop im Teams-Back-End bei einem eingehenden Anruf (PSTN-Benutzer an einen Teams/Bot)-Proxy empfangen hat.<br/>Bei fehlgeschlagenen und nicht beantworteten Anrufen kann dies gleich der Einladungs- oder Fehlerzeit sein. |
> | 6 | Fehlerzeit | `datetimeoffset` | Nur für fehlgeschlagene (nicht vollständig etablierte) Aufrufe vorhanden |
> | 7 | Endzeitpunkt | `datetimeoffset` | Nur für erfolgreiche (vollständig etablierte) Anrufe vorhanden. Uhrzeit, zu der der Anruf beendet wurde |
> | 8 | Dauer (Sekunden) | `int` | Dauer des Anrufs |
> | 9 | Erfolg | `nvarchar(3)` | Ja/Nein. Erfolg oder Versuch |
> | 10 | Rufnummer | `nvarchar(32)` | Die Nummer des Benutzers oder Bots, der bzw. der den Anruf hergestellt hat. Bei einem eingehenden Anruf eines Teambenutzers wird es ein PSTN-Benutzer, beim ausgehenden Anruf des Teams-Benutzers wird die Nummer der Benutzernummer von Teams angezeigt. |
> | 12 | Rufnummer des Anrufs | `nvarchar(32)` | Die Nummer des Benutzers oder Bots, der bzw. der den Anruf empfangen hat. Beim eingehenden Anruf eines Teambenutzers ist dies der Teams-Benutzer, beim ausgehenden Anruf des Teams-Benutzers ist er der PSTN-Benutzer. |
> | 13 | Anruftyp | `nvarchar(32)` | Anruftyp und -richtung |
> | 14 | Azure Region für Medien | `nvarchar(8)` | Das Rechenzentrum, das für den Medienpfad in einem Nichtumgehungsaufruf verwendet wird |
> | 15 | Azure Region für Signalisierung | `nvarchar(8)` | Das Rechenzentrum, das für die Signalisierung sowohl für Umgehungs- als auch nicht-Umgehungsaufrufe verwendet wird |
> | 16 | Endgültiger SIP-Code | `int` | Der Code, mit dem der Aufruf beendet wurde( [RFC 3261)](https://tools.ietf.org/html/rfc3261) |
> | 17 | Endgültiger Microsoft-Untercode | `int` | Zusätzlich zu den SIP-Codes verfügt Microsoft über eigene Untercodes, die das spezifische Problem angeben. |
> | 18 | Endgültiger SIP-Satz | `nvarchar(256)` | Beschreibung des SIP-Codes und des Microsoft-Untercodes |
> | 19 | SBC-FQDN | `nvarchar(64)` | Vollqualifizierter Domänenname des Session Border Controllers |
> | 20 | Medienumgehung | `nvarchar(3)` | Ja/Nein. Gibt an, ob der Trunk für die Medienumgehung aktiviert wurde oder nicht |
> | 21 | Freigegebene Korrelations-ID | `uniqueidentifier` | Gibt an, dass zwei oder mehr Anrufe im Zusammenhang stehen |


## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
