---
title: Microsoft Teams PSTN-Nutzungsbericht
author: LanaChin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie den Bericht "PSTN-Nutzung von Teams" im Microsoft Teams Admin Center verwenden, um einen Überblick über die Verwendung von Anrufen und Audiokonferenzen in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 430ef53d5739a79644a57dbee1c0a30b0ab26852
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827283"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN-Nutzungsbericht

Der Bericht über die PSTN-Nutzung von Teams im Microsoft Teams Admin Center bietet Ihnen einen Überblick über die Aktivitäten von Anrufen und Audiokonferenzen in Ihrer Organisation. Sie können detaillierte Anrufaktivitäten für Anrufpläne anzeigen, wenn Sie Microsoft als Telefonnetzbetreiber und für die direkte Weiterleitung verwenden, wenn Sie Ihren eigenen Telefonnetzbetreiber verwenden.

Auf der Registerkarte " **Anrufpläne** " werden Informationen einschließlich der Anzahl der Minuten angezeigt, die die Benutzer für ein-und ausgehende PSTN-Anrufe und die Kosten für diese Anrufe verwendet haben. Auf der Registerkarte **Direktes Routing** werden Informationen einschließlich der SIP-Adresse und der Anfangs-und Endzeiten des Anrufs angezeigt. Verwenden Sie die Informationen in diesem Bericht, um Einblicke in die PSTN-Nutzung in Ihrer Organisation zu gewinnen und Ihnen zu helfen, Entscheidungen zu untersuchen, zu planen und zu treffen.

## <a name="view-the-report"></a>Anzeigen des Berichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics #a0 Berichte** > **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**den Eintrag **PSTN-Verwendungsbericht**aus.
2. Wählen Sie unter **Datumsbereich**einen vordefinierten Bereich von 7 oder 28 Tage aus, oder legen Sie einen benutzerdefinierten Bereich fest, und wählen Sie dann **Bericht ausführen**aus.

## <a name="interpret-the-report"></a>Interpretieren des Berichts

### <a name="calling-plans"></a>Anrufpläne

![Screenshot des Berichts "Anrufpläne PSTN-Nutzungsbericht" im Admin Center](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "Screenshot des Berichts zur PSTN-Nutzung im Microsoft Teams Admin Center mit nummerierten Beschriftungen")

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht kann für Trends in den letzten 7 Tagen, 28 Tagen oder einem von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt werden. |
|**2**   |Jeder Bericht hat ein Datum, zu dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse ist die Gesamtzahl der Anrufe über den ausgewählten Zeitraum. <br>Zeigen Sie auf den Punkt an einem bestimmten Datum, um die Gesamtzahl der Anrufe an diesem Datum anzuzeigen.  |
|**4**   |In der Tabelle finden Sie eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Username** ist der Anmeldename des Benutzers.</li><li>**Telefonnummer** ist die Nummer, die den Anruf für eingehende Anrufe empfangen hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde.</li><li>**Anruftyp** ist, ob es sich bei dem Anruf um einen PSTN-Ausgangs-oder eingehenden Anruf und die Art des Anrufs, beispielsweise einen Anruf eines Benutzers oder einer Audiokonferenz, handelt. Zu den Anruftypen, die Ihnen möglicherweise angezeigt werden, gehören:<br><br>**Gruppen-Benutzer Anruftypen**<ul><li>**user_in** – der Benutzer hat einen eingehenden PSTN-Anruf erhalten.</li><li>**user_out** – der Benutzer hat einen ausgehenden PSTN-Anruf getätigt.</li><li>**user_out_conf** – der Benutzer hat dem Anruf zwei oder mehr PSTN-Teilnehmer hinzugefügt, beispielsweise ein Konferenzgespräch mit drei Teilnehmern.</li><li>**user_out_transfer** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**user_out_forwarding** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**conf_in** – ein eingehender Anruf an die Audio-Konferenzbrücke</li><li>**conf_out** – ein ausgehender Anruf von der Audiokonferenz-Brücke in der Regel zum Hinzufügen einer PSTN-Nummer zur Konferenz</li></ul><br>**Anrufarten für Teams-Bots**<ul><li>**ucap_in** – ein eingehender PSTN-Anruf an Teams-bot wie automatische Telefonzentrale oder Anrufwarteschlange</li><li>**ucap_out** – ein ausgehender PSTN-Anruf von einem Teams-bot wie einer automatischen Telefonzentrale oder einer Anrufwarteschlange</li></ul><br><li>**Aufgerufen, um** die gewählte Nummer zu wählen.</li><li>**In das Land oder die Region** wird das Land oder die Region gewählt.</li><li>**"Von"** ist die Nummer, die den Anruf getätigt hat.</li><li>**Aus dem Land oder der Region** ist das Land oder die Region, in dem der Anruf getätigt wurde.</li><li>**Gebühren** ist der Betrag des Anrufs, der Ihrem Konto in Rechnung gestellt wird. </li><li>**Währung** ist die Währung, die zum Berechnen der Kosten des Anrufs verwendet wird. </li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>Inland **/International** teilt Ihnen mit, ob es sich um einen Inlandsanruf (innerhalb eines Landes oder einer Region) oder um einen internationalen (außerhalb eines Landes oder einer Region) basierend auf dem Standort des Benutzers handelt.</li><li>**Anruf-ID** ist die ID für einen Anruf. Es ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Microsoft-Support anrufen können.</li><li>**Nummerntyp** ist der Typ der Telefonnummer des Benutzers, beispielsweise ein Dienst mit gebührenfreier Nummer. </li><li>**Land oder Region** ist der Verwendungsstandort. </li> <li>**Konferenz-ID** ist die Konferenz-ID der Audio-Konferenz. </li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den Lizenztypen, die möglicherweise angezeigt werden, gehören:<ul><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** -Domestic Calling Plan (240 min Calling Plan)</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung</li></ul></li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |**Filter** auswählen, um den Bericht nach Benutzername oder Anruftyp zu filtern |
|**7**   |Wählen Sie **Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**8**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf der Registerkarte **Downloads** auf **herunterladen** , um den Bericht herunterzuladen, wenn er fertig ist.|

### <a name="direct-routing"></a>Direktes Routing

![Screenshot des Berichts zur direkten Weiterleitung des PSTN-Nutzungsberichts im Admin Center](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "Screenshot des Berichts zur direkten Weiterleitung der PSTN-Nutzung im Microsoft Teams Admin Center mit nummerierten Beschriftungen")

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht kann für Trends in den letzten 7 Tagen oder 28 Tagen angezeigt werden. |
|**2**   |Jeder Bericht hat ein Datum, zu dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |Die X-Achse ist der ausgewählte Datumsbereich für den jeweiligen Bericht. Die Y-Achse ist die Gesamtzahl der Anrufe über den ausgewählten Zeitraum.<br>Zeigen Sie auf den Punkt an einem bestimmten Datum, um die Gesamtzahl der Anrufe an diesem Datum anzuzeigen.  |
|**4**   |In der Tabelle finden Sie eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Seite "Einstellungen" des Benutzers im Microsoft Teams Admin Center zu wechseln. Der Name kann auch der Name eines bot sein, beispielsweise die Anrufwarteschlange oder die automatische Cloud-Telefonzentrale. </li><li>**SIP-Adresse** ist die SIP-Adresse des Benutzers oder eines bot, der den Anruf erhalten oder getätigt hat.</li><li>**Rufnummernanzeige ist die** Nummer des Benutzers oder des bot, der den Anruf getätigt hat. </li>><li>Die **Nummer des Anrufers** ist die Nummer des Nutzers oder des bot, der den Anruf erhalten hat. Bei einem eingehenden Anruf an einen Teams-Nutzer handelt es sich um den Teams-Nutzer, bei einem ausgehenden Anruf von einem Teams-Nutzer wird es der PSTN-Nutzer sein. </li><li>**Anruftyp** ist, ob es sich bei dem Anruf um einen PSTN-Ausgangs-oder eingehenden Anruf und die Art des Anrufs, beispielsweise einen Anruf eines Benutzers oder einer Audiokonferenz, handelt. Zu den Anruftypen, die Ihnen möglicherweise angezeigt werden, gehören:<br><br>**Gruppen-Benutzer Anruftypen**<ul><li>**dr_in** – der Benutzer hat einen eingehenden PSTN-Anruf erhalten</li><li>**dr_out** – der Benutzer hat einen ausgehenden PSTN-Anruf getätigt.</li><li>**dr_out_user_conf** – der Benutzer hat dem Anruf einen PSTN-Teilnehmer hinzugefügt.</li><li>**user_out_transfer** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_forwarding** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_transfer** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_emergency_out** – der Benutzer hat einen Notruf getätigt</li></ul><br>**Anrufarten für Teams-Bots**<ul><li>**dr_in_ucap** – ein eingehender PSTN-Anruf an einen Teams-bot wie automatische Telefonzentrale oder Anrufwarteschlange</li><li>**dr_out_ucap** – ein ausgehender PSTN-Anruf von einem Teams-bot wie einer automatischen Telefonzentrale oder einer Anrufwarteschlange</li></ul><br><li>**Called to** ist die Nummer des Benutzers, der den Anruf erhalten hat.</li><li>**Startzeit (UTC)** ist der Zeitpunkt, zu dem der SIP-Proxy die endgültige Antwort erhalten hat (SIP-Nachricht "200 OK") aus dem SBC bei einem ausgehenden Anruf (Teams/bot an einen PSTN-Benutzer) oder nachdem der SIP-Proxy die Einladung an den nächsten Hop innerhalb des Teams-Back-Ends bei einem eingehenden Anruf (PSTN-Benutzer zu einem Team/bot) </li><li>**Einladungs Zeit (UTC)** ist der Zeitpunkt, zu dem die erste Einladung über einen ausgehenden Anruf von einem Teams-Benutzer oder bot-Anruf an den SBC gesendet oder bei einem eingehenden Anruf an einen Teams oder bot-Anruf durch die SIP-Proxy Komponente des direkten Routings vom SBC empfangen wurde.</li><li>**Fehlerzeit (UTC)** ist der Zeitpunkt, zu dem der Anruf fehlgeschlagen ist. Nur für fehlgeschlagene Anrufe. Der endgültige SIP-Code, der endgültige Microsoft-unter Code und der endgültige SIP-Ausdruck bieten die Gründe für den Fehler des Anrufs und können bei der Problembehandlung helfen. </li><li>**Endzeit (UTC)** ist der Zeitpunkt, zu dem der Anruf beendet wurde (nur für erfolgreiche Anrufe).</li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**Nummerntyp** ist der Typ der Telefonnummer des Benutzers, beispielsweise ein Dienst mit gebührenfreier Nummer. </li><li>**Medienumgehung** gibt an, ob der Trunk für die medienumgehung aktiviert wurde. </li> <li>Der **SBC-FQDN** ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Session Border Controllers (SBC). </li><li>Der **Azure-Bereich für Medien** ist das Rechenzentrum, das in einem nicht-Bypass-Anruf als Medienpfad verwendet wurde. </li><li>Der **Azure-Bereich für Signalisierungen** ist das Rechenzentrum, das für die Signalisierung sowohl für Bypass-als auch für nicht-Bypass-Anrufe verwendet wurde. </li><li>**Event Type** ist der Ereignistyp des Anrufs. Sie sehen Erfolg für erfolgreiche Anrufe und versuchen, fehlgeschlagene Anrufe zu führen. </li><li>Der **endgültige SIP-Code** ist der Code, mit dem der Anruf beendet wurde.</li><li>Der **endgültige Microsoft** -unter Code ist ein Code, der bestimmte Aktionen angibt, die aufgetreten sind.</li><li>**Endgültige SIP-Phrase** ist die Beschreibung des SIP-Codes und des Microsoft-Subcodes.</li><li>**Korrelations-ID** ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Aufrufen des Microsoft-Supports verwenden können.</li><li>Die **freigegebene Korrelations-ID** wird nur in der herunterladbaren CSV-Datei angezeigt und ist nicht im Portal vorhanden. Die freigegebene Korrelations-ID ist in mindestens zwei Anrufen vorhanden, die miteinander verknüpft sind. Eine detaillierte Beschreibung finden Sie unten.</li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen Sie **Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**7**   |Wählen Sie in **Excel exportieren** aus, um die Daten in einer durch Kommas getrennten Datei (CSV) für die Offlineanalyse herunterzuladen oder als Eingabe für Ihr Abrechnungssystem zu verwenden. |

**Überlegungen zu den Feldern für Anrufer/Anrufer**

In Abhängigkeit von der Anrufrichtung können die Namen von Anrufern oder aufgerufenen nicht-E164-Nummern enthalten.

Diese Felder können von den Kunden-SBC (s) stammen. Es gibt drei Formate, die SBC an Direct Routing senden kann: e. 164-Nummern, nicht-E. 164-Nummern und Zeichenfolgen.

- E. 164-Telefonnummer eines Benutzers mit einer e. 164-Nummer für einen Benutzer, der auch eine e. 164-Nummer hat. 
- Anruf über eine nicht-E. 164-Nummer. Ein Benutzer von einer Drittanbieter-Telefonanlage, die mit direktem Routing verbunden ist, führt einen Anruf an einen Teams-Benutzer. In diesem Fall kann die Rufnummernanzeige eine beliebige nicht-E. 164-Nummer sein, beispielsweise + 1001. 
- Ein Spammer ruft keine Nummer, sondern nur einen Namen auf, beispielsweise "Internal Revenue Service". Diese Zeichenfolge wird in den Berichten angezeigt.

**Informationen zur freigegebenen Korrelations-ID**

Die freigegebene Korrelations-ID ist nur in der exportierten Excel-Datei vorhanden, die Sie herunterladen, und gibt an, dass zwei oder mehr Anrufe verknüpft sind. Im folgenden werden die verschiedenen Szenarien erläutert, und wenn die freigegebene Korrelations-ID vorhanden ist.

1.  PSTN-Benutzer 1 auf einem PSTN-Endpunkt mit dem Namen "Teams-Benutzer 1" im Team-Client, Anruftyp Dr_In, Korrelations-ID 57f28917-42k5-4c0c-9433-79734873f2ac, keine freigegebene Korrelations-ID.
2.  Teams Benutzer 1 im Teams-Client mit dem Namen PSTN-Benutzer 1 auf einem PSTN-Endpunkt, Anruftyp Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, keine freigegebene Korrelations-ID.
3.  PSTN-Benutzer 1 auf einem PSTN-Endpunkt, der als Teams-Benutzer 2 auf dem Microsoft Teams-Client bezeichnet wird, Typ Dr_In f45e9a25-9f94-46e7-A457-84f5940efde9, freigegebene Korrelations-ID f45e9a25-9f94-46e7-A457-84f5940efde9.
4.  Vorhandener Anruf 3 mit Korrelations-ID "f45e9a25-9f94-46e7-A457-84f5940efde9". PSTN-Benutzer 1 in einem Anruf mit Teams User 2. Teams Benutzer 2 übertragen (Blind oder beratend) einen Anruf an Teams oder PSTN-Benutzer, Anruftyp Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, freigegebene Korrelations-ID f45e9a25-9f94-46e7-A457-84f5940efde9.

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
