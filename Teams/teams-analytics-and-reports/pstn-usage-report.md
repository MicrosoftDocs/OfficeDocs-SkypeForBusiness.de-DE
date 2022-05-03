---
title: Microsoft Teams PSTN-Verwendungsbericht
author: SerdarSoysal
ms.author: serdars
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
description: Erfahren Sie, wie Sie den Bericht zur Teams PSTN-Nutzung im Microsoft Teams Admin Center verwenden, um einen Überblick über die Verwendung von Anrufen und Audiokonferenzen in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d94056db364e52053b8c676cb1e331ace81f540d
ms.sourcegitcommit: 9f7372f7568b4275169590510d2b7a0c0ad7577b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2022
ms.locfileid: "65171721"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN-Verwendungsbericht

Der Nutzungsbericht Teams PSTN (Public Switched Telephone Network) im Microsoft Teams Admin Center bietet Ihnen einen Überblick über die Anruf- und Audiokonferenzaktivitäten in Ihrer Organisation. Sie können detaillierte Anrufaktivitäten für Anrufpläne anzeigen, wenn Sie Microsoft als Telefonieanbieter und Direct Routing verwenden, wenn Sie Ihren eigenen Telefonieanbieter verwenden.

Auf der Registerkarte **"Anrufpläne** " werden Informationen angezeigt, einschließlich der Anzahl der Minuten, die Benutzer für eingehende und ausgehende PSTN-Anrufe aufgewendet haben, und die Kosten für diese Anrufe. Auf der Registerkarte " **Direct Routing** " werden Informationen angezeigt, einschließlich der SIP-Adresse sowie der Start- und Endzeiten von Anrufen. Verwenden Sie die Informationen in diesem Bericht, um Einblicke in die PSTN-Nutzung in Ihrer Organisation zu erhalten und Ihnen zu helfen, Geschäftsentscheidungen zu untersuchen, zu planen und zu treffen.

> [!NOTE]
> Wenn Sie über einen Telstra- oder Softbank-Anrufplan verfügen, werden keine Anrufdetaildatensätze im PSTN-Nutzungsbericht angezeigt. Bitte wenden Sie sich an Telstra oder Softbank, um Ihre Berichterstellungsanforderungen zu erfüllen. 

## <a name="view-the-pstn-usage-report"></a>Anzeigen des PSTN-Verwendungsberichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf **Analytics &** **ReportsUsage-Berichte** > . Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht**" den **PSTN-Verwendungsbericht** aus.
2. Wählen Sie unter **"Datumsbereich**" einen vordefinierten Bereich von 7 oder 28 Tagen aus, oder legen Sie einen benutzerdefinierten Bereich fest, und wählen Sie dann " **Bericht ausführen**" aus.

## <a name="interpret-the-report"></a>Interpretieren des Berichts

### <a name="calling-plans"></a>Anrufpläne

   ![Screenshot des PSTN-Nutzungsberichts für Anrufpläne im Admin Center](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Screenshot des PSTN-Nutzungsberichts im Microsoft Teams Admin Center mit nummerierten Legenden](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht kann nach Trends über die letzten 7 Tage, 28 Tage oder einen von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt werden. |
|**2**   |Jeder Bericht hat ein Datum für die Generierung. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse ist die Gesamtanzahl der Aufrufe im ausgewählten Zeitraum. <br>Zeigen Sie mit der Maus auf den Punkt an einem bestimmten Datum, um die Gesamtanzahl der Anrufe an diesem Datum anzuzeigen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist die Zeit, zu der der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Benutzername** ist der Anmeldename des Benutzers.</li><li>**Telefon Nummer** ist die Nummer, die den Anruf für eingehende Anrufe erhalten hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde.</li><li>**Der Anruftyp** ist, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PSTN-Anruf handelt, und um die Art des Anrufs, z. B. einen Anruf, der von einem Benutzer oder einer Audiokonferenz getätigt wurde. Zu den angezeigten Anruftypen gehören:<br><br>**Teams von Benutzeranruftypen**<ul><li>**user_in** – Der Benutzer hat einen eingehenden PSTN-Anruf erhalten.</li><li>**user_out** – Der Benutzer hat einen ausgehenden PSTN-Anruf getätigt.</li><li>**user_out_conf** – Der Benutzer hat dem Anruf zwei oder mehr PSTN-Teilnehmer hinzugefügt, z. B. eine dreistufige Telefonkonferenz.</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**user_out_forwarding** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**conf_in** – ein eingehender Anruf an die Audiokonferenzbrücke</li><li>**conf_out** – ein ausgehender Anruf von der Audiokonferenzbrücke, um der Konferenz normalerweise eine PSTN-Nummer hinzuzufügen.</li><li>**unassigned_in** – ein eingehender PSTN-Anruf über den Anrufplan an eine nicht zugewiesene Nummer</li></ul><br>**Teams Bots-Anruftypen**<ul><li>**ucap_in** – ein eingehender PSTN-Anruf an Teams Bot, z. B. die automatische Telefonzentrale oder die Anrufwarteschleife</li><li>**ucap_out** – ein ausgehender PSTN-Anruf von einem Teams Bot, z. B. von der automatischen Telefonzentrale oder der Anrufwarteschleife</li></ul><br><li>**Angerufen wird** die gewählte Nummer.</li><li>**In land oder region** ist das Land oder die Region gewählt.</li><li>**Angerufen von** ist die Nummer, die den Anruf getätigt hat.</li><li>**Von Land oder Region** ist das Land oder die Region, aus dem bzw. der der Anruf getätigt wurde.</li><li>**Die Gebühr** ist der Betrag oder die Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird. </li><li>**Währung** ist die Art der Währung, die zum Berechnen der Kosten des Anrufs verwendet wird. </li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**National/International** teilt Ihnen mit, ob der Anruf inländischer (innerhalb eines Landes oder einer Region) oder international (außerhalb eines Landes oder einer Region) war, basierend auf dem Standort des Benutzers.</li><li>**Anruf-ID** ist die ID für einen Anruf. Es handelt sich um einen Bezeichner für den Anruf, den Sie beim Aufrufen Microsoft-Support verwenden können.</li><li>**Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. ein Dienst mit gebührenfreier Nummer. </li><li>**Land oder Region** ist der Verwendungsort. </li> <li>**Konferenz-ID** ist die Konferenz-ID der Audiokonferenz. </li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den angezeigten Lizenztypen gehören:<ul><li>**MCOEV oder MCOEV_VIRTUALUSER oder MCOEV_VIRTUALUSER_GOV** – VoIP-Anwendungen wie automatische Telefonzentrale oder Anrufwarteschleifen</li><li>**FREECALL** - Im Falle eines technischen Problems, das uns daran hindert, einen Anruf zu bepreisen, wird der Anruf kostenlos bereitgestellt und wird mit dieser Funktion angezeigt</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** – Anrufplan für Inland (240 Minuten Anrufplan)</li><li>**MCOPSTN8** – Anrufplan für Inland 120 Minuten pro Benutzer (nicht über Benutzer hinweg zusammengefasst wie die anderen Anrufpläne)</li><li>**MCOPSTN9** - Internationaler Anrufplan</li><li>**MCOPSTNCAP** – Telefon</li><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETADD_DIALOUT_US** – Einwahlplan für Audiokonferenzen in den USA und Kanada</li><li>**MCOMEETADD_CN_GLOBAL** – Audiokonferenzen für Nicht-China-Benutzer</li><li>**MCOMEETADD_TATA** – Tata Communications Connections</li><li>**MCOMEETACPEA** - Audiokonferenzen pay-per-minute </li><li>**MCOMEETACPEA_GOV** – Audiokonferenzen per Minuten-Pay-per-Minute für Behörden</li></ul></li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen Sie **"Filtern** " aus, um den Bericht nach Benutzername oder Anruftyp zu filtern. |
|**7**   |Wählen Sie **"Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**8**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **"Exportieren", um Excel**, und klicken Sie dann auf der Registerkarte "**Downloads**" auf "**Herunterladen**", um den Bericht herunterzuladen, wenn er bereit ist.|

### <a name="direct-routing"></a>Direct Routing

   ![Screenshot des Berichts "Direct Routing PSTN Usage" im Admin Center](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Screenshot des Direct Routing-PSTN-Verwendungsberichts im Microsoft Teams Admin Center mit nummerierten Legenden](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht kann nach Trends in den letzten 7 Tagen oder 28 Tagen angezeigt werden. |
|**2**   |Jeder Bericht hat ein Datum für die Generierung. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse ist die Gesamtanzahl der Aufrufe im ausgewählten Zeitraum.<br>Zeigen Sie mit der Maus auf den Punkt an einem bestimmten Datum, um die Gesamtanzahl der Anrufe an diesem Datum anzuzeigen.  |
|**4**   |Die Tabelle enthält eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist die Zeit, zu der der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. Der Name kann auch der Name eines Bots sein, z. B. die Anrufwarteschleife oder die automatische Cloudtelefonzentrale. </li><li>**SIP-Adresse** ist die SIP-Adresse des Benutzers oder Bots, der den Anruf empfangen oder getätigt hat.</li><li>**Die Anrufernummer** ist die Nummer des Benutzers oder Bots, der den Anruf getätigt hat. </li><li>**Die Nummer des Angerufenen** ist die Nummer des Benutzers oder Bots, der den Anruf erhalten hat. Bei einem eingehenden Anruf an einen Teams Benutzer ist es der Teams Benutzer, bei einem ausgehenden Anruf von einem Teams Benutzer ist es der PSTN-Benutzer. </li><li>**Der Anruftyp** ist, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PSTN-Anruf handelt, und um die Art des Anrufs, z. B. einen Anruf, der von einem Benutzer oder einer Audiokonferenz getätigt wurde. Zu den Angezeigten Anruftypen gehören:<br><br>**Teams von Benutzeranruftypen**<ul><li>**dr_in** – Der Benutzer hat einen eingehenden PSTN-Anruf erhalten.</li><li>**dr_out** – Der Benutzer hat einen ausgehenden PSTN-Anruf getätigt.</li><li>**dr_out_user_conf** – Der Benutzer hat dem Anruf einen PSTN-Teilnehmer hinzugefügt.</li><li>**user_out_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_forwarding** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_transfer** – Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_emergency_out** – Der Benutzer hat einen Notruf getätigt</li><li>**dr_unassigned_in** – ein eingehender PSTN-Anruf über Direct Routing an eine nicht zugewiesene Nummer</li></ul><br>**Teams Bots-Anruftypen**<ul><li>**dr_in_ucap** – ein eingehender PSTN-Anruf an einen Teams Bot, z. B. die automatische Telefonzentrale oder die Anrufwarteschleife</li><li>**dr_out_ucap** – ein ausgehender PSTN-Anruf von einem Teams Bot, z. B. von der automatischen Telefonzentrale oder der Anrufwarteschleife</li></ul><br><li>**Angerufen an** ist die Nummer des Benutzers, der den Anruf erhalten hat.</li><li>**Die Startzeit (UTC)** ist die Zeit, zu der der SIP-Proxy die endgültige Antwort (SIP-Nachricht "200 OK") vom SBC bei einem ausgehenden Anruf (Teams/Bot an einen PSTN-Benutzer) oder nachdem der SIP-Proxy die Einladung an den nächsten Hop innerhalb des Teams Back-End bei einem eingehenden Anruf (PSTN-Benutzer an einen Teams/Bot) gesendet hat. </li><li>**Die Einladungszeit (UTC)** ist die Zeit, zu der die anfängliche Einladung bei einem ausgehenden Anruf von einem Teams Benutzer- oder Botanruf an den SBC gesendet oder bei einem eingehenden Anruf an einen Teams- oder Botanruf von der SIP-Proxykomponente von Direct Routing vom SBC empfangen wurde.</li><li>**Die Fehlerzeit (UTC)** ist der Zeitpunkt, zu dem der Aufruf fehlgeschlagen ist. Nur für fehlgeschlagene Anrufe. Final SIP Code, Final Microsoft Subcode, and Final SIP Phrase provide the reasons why the call failed and can help with troubleshooting. </li><li>**Endzeit (UTC)** ist die Uhrzeit, zu der der Anruf beendet wurde (nur für erfolgreiche Anrufe).</li><li>**Dauer** ist, wie lange der Anruf verbunden war, von der Einladung bis zum Anrufende oder fehler. Bei der Anrufweiterleitung umfasst die Dauer das Klingeln in der Anrufwarteschleife.</li><li>**Nummerntyp** ist der Telefonnummerntyp des Benutzers, z. B. ein Dienst mit gebührenfreier Nummer. </li><li>**Die Medienumgehung** gibt an, ob der Trunk für die Medienumgehung aktiviert wurde. </li> <li>**SBC-FQDN** ist der vollqualifizierte Domänenname (FQDN) des Session Border Controller (SBC). </li><li>**Azure-Region für Medien** ist das Rechenzentrum, das in einem Nichtumgehungsaufruf als Medienpfad verwendet wurde. </li><li>**Azure-Region für die Signalisierung** ist das Rechenzentrum, das für die Signalisierung sowohl für Umgehungs- als auch für Nichtumgehungsaufrufe verwendet wurde. </li><li>**Der Ereignistyp** ist der Ereignistyp des Aufrufs. "Erfolgreich" für erfolgreiche Anrufe und "Versuch für fehlgeschlagene Anrufe" wird angezeigt. </li><li>**Der endgültige SIP-Code** ist der Code, mit dem der Aufruf beendet wurde.</li><li>**Final Microsoft subcode** is a code that indicates specific actions that occurred.</li><li>**Der letzte SIP-Ausdruck** ist die Beschreibung des SIP-Codes und der Microsoft-Untercodierung.</li><li>**Die Korrelations-ID** ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Aufrufen Microsoft-Support verwenden können.</li><li>**Die freigegebene Korrelations-ID** ist nur in der herunterladbaren CSV-Datei sichtbar und im Portal nicht vorhanden. Die freigegebene Korrelations-ID ist in mindestens zwei Aufrufen vorhanden, die miteinander verknüpft sind. Bitte sehen Sie sich die ausführliche Beschreibung unten an.</li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen Sie **"Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**7**   |Wählen Sie **"Exportieren" aus, um Excel**, um die Daten in einer durch Trennzeichen getrennten Datei (CSV) für die Offlineanalyse herunterzuladen oder als Eingabe für Ihr Abrechnungssystem zu verwenden. |

#### <a name="callercallee-fields-considerations"></a>Überlegungen zu Feldern für Anrufer/Angerufene

Je nach Anrufrichtung können die Namen des Anrufers oder des Angerufenen Nicht-E164-Nummern enthalten.

Diese Felder können von den Kunden-SBC(s) stammen. Es gibt drei Formate, die der SBC an Direct Routing senden kann: E.164-Nummern, Nicht-E.164-Nummern und Zeichenfolgen.

- E.164-Telefonnummer eines Benutzers, der über eine E.164-Nummer verfügt, an einen Benutzer, der auch über eine E.164-Nummer verfügt. 
- Anrufen von einer Nicht-E.164-Nummer. Ein Benutzer von einer mit Direct Routing verbundenen Nebenstellenanlage eines Drittanbieters ruft einen Teams Benutzer an. In diesem Fall kann es sich bei der Anrufernummer um eine beliebige Nummer ungleich E.164 handeln, z. B. +1001. 
- Ein Spammer ruft an und zeigt keine Nummer an, nur einen Namen, z. B. "Internal Revenue Service". Diese Zeichenfolge wird in den Berichten angezeigt.

#### <a name="phone-number-obfuscation"></a>Telefon Zahlenverschleifung
Die Datenschutzanforderungen pro Land umfassen die Verschleierung der externen Telefonnummern (die nicht im Besitz des Kunden sind). Die drei oder vier letzten Ziffern der Telefonnummer werden durch Sternchen (+123 456789***) ersetzt. 

Für die eingehenden Anrufe ist die Anrufernummer verschleiert, bei ausgehenden Anrufen ist die Nummer des Angerufenen verschleiert. Dies gilt für die PSTN- und Direct Routing-Berichte im Mandanten-Admin Center, den Datenexport und die über Microsoft Graph verfügbaren Anrufprotokolle.

Die Verschleierung basiert auf dem Standort (Land) der Organisation. Vollständige Telefonnummern werden für die Länder angezeigt, die in der folgenden Tabelle nicht aufgeführt sind:

| Land | Anzahl der Verschleierungsziffern |
| :-: | :- |
|BE – Belgien | 3 |
|CH – Schweiz | 4 |
|DE - Deutschland | 3 |
|DK – Dänemark | 3 |
|ES – Spanien | 3 |
|FI – Finnland | 3 |
|FR – Frankreich | 4 |
|IT – Italien | 3 |
|NL - Niederlande | 3 |
|NEIN - Norwegen | 3 |
|SE - Schweden | 3 |

#### <a name="about-shared-correlation-id"></a>Informationen zur gemeinsamen Korrelations-ID

Die freigegebene Korrelations-ID ist nur in der exportierten Excel Datei vorhanden, die Sie herunterladen, und gibt an, dass zwei oder mehr Aufrufe im Zusammenhang stehen. Im Folgenden werden die verschiedenen Szenarien und der Zeitpunkt erläutert, an dem die freigegebene Korrelations-ID vorhanden ist.

1.    PSTN-Benutzer 1 auf einem PSTN-Endpunkt namens Teams Benutzer 1 auf Teams Client, Anruftyp Dr_In, Korrelations-ID 57f28917-42k5-4c0c-9433-79734873f2ac, keine freigegebene Korrelations-ID.
2.    Teams Benutzer 1 auf Teams Client namens PSTN-Benutzer 1 auf einem PSTN-Endpunkt, Anruftyp Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, keine freigegebene Korrelations-ID.
3.    PSTN-Benutzer 1 auf einem PSTN-Endpunkt, der als Teams Benutzer 2 auf Teams Client bezeichnet wird, Anruftyp Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9, freigegebene Korrelations-ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4.    Vorhandener Anruf 3 mit Korrelations-ID "f45e9a25-9f94-46e7-a457-84f5940efde9". PSTN-Benutzer 1 in einem Anruf mit Teams Benutzer 2. Teams Benutzer 2 einen Anruf an Teams oder PSTN-Benutzer durchgestellt (blind oder beratend), Anruftyp Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, shared correlation ID f45e9a25-9f94-46e7-a457-84f5940efde9.

## <a name="exporting-the-reports"></a>Exportieren der Berichte
Klicken Sie auf **"Exportieren", um Excel**, und klicken Sie dann auf der Registerkarte "**Downloads**" auf "**Herunterladen**", um den Bericht herunterzuladen, wenn er bereit ist. Der Exportvorgang kann je nach Menge der Daten von einigen Sekunden bis zu mehreren Minuten dauern.

Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Exportierte Dateien enthalten zusätzliche Felder, die im Onlinebericht nicht verfügbar sind. Diese können für die Problembehandlung und automatisierte Workflows verwendet werden.

 Sie erhalten eine ZIP-Datei mit dem Namen "**Calls.Export.`[identifier]`.zip**", wobei der Bezeichner eine eindeutige ID für den Export ist, der für die Problembehandlung verwendet werden kann.

Wenn Sie sowohl Anrufpläne als auch Direct Routing haben, kann die exportierte Datei Daten für beide Produkte enthalten. Die PSTN-Verwendungsberichtsdatei weist den Dateinamen "**PSTN.calls" auf.`[UTC date]`.csv**" und Direct Routing "**DirectRouting.calls.`[UTC date]`.csv**".

 Zusätzlich zu PSTN- und Direct Routing-Dateien enthält das Archiv die Datei "**parameters.json**" mit dem ausgewählten Exportzeitbereich und den ausgewählten Funktionen.

Exportierte Dateien sind im CSV-Format (Comma Separated Values) und entsprechen dem [RFC 4180-Standard](https://tools.ietf.org/html/rfc4180) . Die Dateien können in Excel oder einem anderen standardkonformen Editor geöffnet werden, ohne dass Transformationen erforderlich sind.

Die erste Zeile der CSV-Datei enthält Spaltennamen. Alle Datumsangaben sind UTC und im [ISO 8601-Format](https://en.wikipedia.org/wiki/ISO_8601) .

### <a name="exported-pstn-usage-report"></a>Exportierter PSTN-Verwendungsbericht

 Sie können Daten bis zu einem Jahr ab dem aktuellen Datum exportieren, es sei denn, länderspezifische Vorschriften verbieten die Aufbewahrung der Daten für 12 Monate.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Eindeutiger Anrufbezeichner |
> | 1 | Anruf-ID | `nvarchar(64)` | Anrufbezeichner. Nicht garantiert einzigartig |
> | 2 | Konferenz-ID | `nvarchar(64)` | ID der Audiokonferenz |
> | 3 | Benutzerspeicherort | `nvarchar(2)` | Ländercode des Benutzers, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Aufrufen der Benutzer-ID in Azure Active Directory.<br/> Diese und andere Benutzerinformationen sind für Bot-Anruftypen null/leer (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (Anmeldename) in Azure Active Directory.<br/>Dies ist in der Regel identisch mit der SIP-Adresse des Benutzers und kann mit der E-Mail-Adresse des Benutzers identisch sein. |
> | 6 | Anzeigename des Benutzers | `nvarchar(128)` | Anzeigename des Benutzers |
> | 7 | Anrufer-ID | `nvarchar(128)` | Nummer, die den Anruf für eingehende Anrufe oder die für ausgehende Anrufe gewählte Nummer erhalten hat. [E.164-Format](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Anruftyp | `nvarchar(32)` | Gibt an, ob es sich bei dem Anruf um einen ausgehenden oder eingehenden PSTN-Anruf handelt und um die Art des Anrufs, z. B. einen Anruf eines Benutzers oder eine Audiokonferenz. |
> | 9 | Zahlentyp | `nvarchar(16)` | Telefonnummerntyp des Benutzers, z. B. ein Dienst mit gebührenfreier Telefonnummer |
> | 10 | Inland/International | `nvarchar(16)` | Ob der Anruf inländischer (innerhalb eines Landes oder einer Region) oder international (außerhalb eines Landes oder einer Region) war, basierend auf dem Standort des Benutzers |
> | 11 | Gewähltes Ziel | `nvarchar(64)` | Gewähltes Land oder Region |
> | 12 | Zielnummer | `nvarchar(32)` | Gewählte Nummer im [E.164-Format](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Startzeit | `datetimeoffset` | Startzeit des Anrufs |
> | 14 | Endzeit | `datetimeoffset` | Anrufendzeit |
> | 15 | Dauer Sekunden | `int` | Wie lange der Anruf verbunden war |
> | 16 | Verbindungsgebühr | `numeric(16, 2)` | Verbindungsgebührenpreis |
> | 17 | Berechnen | `numeric(16, 2)` | Betrag oder Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird |
> | 18 | Währung | `nvarchar(3)` | Zum Berechnen der Kosten des Anrufs verwendeter Währungstyp ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funktion | `nvarchar(32)` | Die für den Anruf verwendete Lizenz |

### <a name="exported-direct-routing-usage-report"></a>Exportierter Direct Routing-Verwendungsbericht

Sie können Daten bis zu fünf Monate (150 Tage) ab dem aktuellen Datum exportieren, es sei denn, länderspezifische Vorschriften verbieten die Aufbewahrung der Daten für diesen Zeitraum.

> [!div class="has-no-wrap"]  
> | # | Name | [Datentyp (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | Correlationid | `uniqueidentifier` | Anrufbezeichner. Mehrere Abschnitte desselben Aufrufs können dieselbe CorrelationId verwenden. |
> | 1 | AAD ObjectId | `uniqueidentifier` | Aufrufen der Benutzer-ID in Azure Active Directory.<br/> Diese und andere Benutzerinformationen können für Bot-Anruftypen null/leer sein. |
> | 2 | UPN | `nvarchar(128)` | UserPrincipalName (Anmeldename, Azure Active Directory) des Benutzers oder Bots, der den Anruf getätigt oder empfangen hat.<br/>Dies ist in der Regel identisch mit der SIP-Adresse des Benutzers und kann mit der E-Mail-Adresse des Benutzers identisch sein. |
> | 3 | Display Name | `nvarchar(128)` | Der Name eines Benutzers oder eines aufrufenden Bots (z. B. Anrufwarteschleife oder automatische Telefonzentrale), wie in Microsoft 365 Admin Center |
> | 4 | Benutzerland | `nvarchar(2)` | Ländercode des Benutzers, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | Einladungszeitpunkt | `datetimeoffset` | Wenn die anfängliche Einladung ausgehend von Teams Benutzer- oder Botanruf an den SBC gesendet oder beim Eingehenden an Teams- oder Botanruf von der SIP-Proxykomponente von Direct Routing vom SBC empfangen wird |
> | 6 | Startzeitpunkt | `datetimeoffset` | Zeitpunkt, zu dem der SIP-Proxy die endgültige Antwort (SIP-Nachricht "200 OK") vom SBC bei ausgehendem (Teams/Bot an einen PSTN-Benutzer) oder nachdem der SIP-Proxy die Einladung an den nächsten Hop innerhalb Teams Back-End bei eingehendem Anruf (PSTN-Benutzer an einen Teams/Bot) gesendet hat.<br/>Bei fehlgeschlagenen und unbeantworteten Anrufen kann dies der Einladungs- oder Fehlerzeit entsprechen. |
> | 7 | Fehlerzeit | `datetimeoffset` | Nur für fehlgeschlagene (nicht vollständig eingerichtete) Aufrufe vorhanden |
> | 8 | Endzeitpunkt | `datetimeoffset` | Nur für erfolgreiche (vollständig eingerichtete) Aufrufe vorhanden. Zeitpunkt, zu dem der Anruf beendet wurde |
> | 9 | Dauer (Sekunden) | `int` | Dauer des Anrufs, von der Einladung bis zum Anrufende oder Fehler. Bei der Anrufweiterleitung umfasst die Dauer das Klingeln in der Anrufwarteschleife. |
> | 10 | Erfolg | `nvarchar(3)` | Ja/Nein. Erfolg oder Versuch |
> | 11 | Anrufernummer | `nvarchar(32)` | Die Nummer des Benutzers oder Bots, der den Anruf getätigt hat. Bei eingehendem Anruf eines Teambenutzers ist es ein PSTN-Benutzer, bei ausgehendem Anruf von Teams Benutzer ist dies die Teams Benutzernummer. |
> | 12 | Nummer des Angerufenen | `nvarchar(32)` | Die Nummer des Benutzers oder Bots, der den Anruf erhalten hat. Bei eingehendem Anruf eines Teambenutzers ist es der Teams Benutzer, bei ausgehendem Anruf von Teams Benutzer ist es der PSTN-Benutzer. |
> | 13 | Anruftyp | `nvarchar(32)` | Anruftyp und -richtung |
> | 14 | Azure-Region für Medien | `nvarchar(8)` | Das Rechenzentrum, das für den Medienpfad beim Nichtumgehungsaufruf verwendet wird |
> | 15 | Azure-Region für die Signalisierung | `nvarchar(8)` | Das Rechenzentrum, das für die Signalisierung sowohl für Umgehungs- als auch für Nichtumgehungsaufrufe verwendet wird |
> | 16 | Endgültiger SIP-Code | `int` | Der Code, mit dem der Aufruf beendet wurde, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | Endgültige Microsoft-Untercodierung | `int` | Zusätzlich zu den SIP-Codes verfügt Microsoft über eigene Untercodes, die das spezifische Problem angeben. |
> | 18 | Letzter SIP-Ausdruck | `nvarchar(256)` | Beschreibung des SIP-Codes und des Microsoft-Untercodes |
> | 19 | SBC-FQDN | `nvarchar(64)` | Vollqualifizierter Domänenname des Sitzungsrahmencontrollers |
> | 20 | Medienumgehung | `nvarchar(3)` | Ja/Nein. Gibt an, ob der Trunk für die Medienumgehung aktiviert wurde oder nicht. |
> | 21 | Gemeinsame Korrelations-ID | `uniqueidentifier` | Gibt an, dass zwei oder mehr Anrufe im Zusammenhang stehen |


## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [PSTN-Anrufbericht in Microsoft Graph](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Direct Routing-Bericht in Microsoft Graph](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)
