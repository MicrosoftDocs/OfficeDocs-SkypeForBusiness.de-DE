---
title: Microsoft Teams PSTN-Nutzungsbericht
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Hier erfahren Sie, wie Sie den Bericht "PSTN-Nutzung von Teams" im Microsoft Teams Admin Center verwenden, um einen Überblick über die Verwendung von Anrufen und Audiokonferenzen in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89d33f15401d25767c905f16e38d93744d7929c3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570566"
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
|**4**   |In der Tabelle finden Sie eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**Username** ist der Anmeldename des Benutzers.</li><li>**Telefonnummer** ist die Nummer, die den Anruf für eingehende Anrufe empfangen hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde.</li><li>**Anruftyp** ist, ob es sich bei dem Anruf um einen PSTN-Ausgangs-oder eingehenden Anruf und die Art des Anrufs, beispielsweise einen Anruf eines Benutzers oder einer Audiokonferenz, handelt. Zu den Anruftypen, die Ihnen möglicherweise angezeigt werden, gehören:<br><br>**Gruppen-Benutzer Anruftypen**<ul><li>**user_in** – der Benutzer hat einen eingehenden PSTN-Anruf erhalten.</li><li>**user_out** – der Benutzer hat einen ausgehenden PSTN-Anruf getätigt</li><li>**user_out_conf** – der Benutzer hat dem Anruf zwei oder mehr PSTN-Teilnehmer hinzugefügt, beispielsweise ein Konferenzgespräch mit drei Teilnehmern.</li><li>**user_out_transfer** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**user_out_forwarding** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**conf_in** – ein eingehender Anruf an die Audio-Konferenzbrücke</li><li>**conf_out** – ein ausgehender Anruf von der Audio-Konferenzbrücke in der Regel, um der Konferenz eine PSTN-Nummer hinzuzufügen</li></ul><br>**Anrufarten für Teams-Bots**<ul><li>**ucap_in** – ein eingehender PSTN-Anruf an Teams-bot wie automatische Telefonzentrale oder Anrufwarteschlange</li><li>**ucap_out** – ein ausgehender PSTN-Anruf von einem Teams-bot wie einer automatischen Telefonzentrale oder einer Anrufwarteschlange</li></ul><br><li>**Aufgerufen, um** die gewählte Nummer zu wählen.</li><li>**In das Land oder die Region** wird das Land oder die Region gewählt.</li><li>**"Von"** ist die Nummer, die den Anruf getätigt hat.</li><li>**Aus dem Land oder der Region** ist das Land oder die Region, in dem der Anruf getätigt wurde.</li><li>**Gebühren** ist der Betrag des Anrufs, der Ihrem Konto in Rechnung gestellt wird. </li><li>**Währung** ist die Währung, die zum Berechnen der Kosten des Anrufs verwendet wird. </li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>Inland **/International** teilt Ihnen mit, ob es sich um einen Inlandsanruf (innerhalb eines Landes oder einer Region) oder um einen internationalen (außerhalb eines Landes oder einer Region) basierend auf dem Standort des Benutzers handelt.</li><li>**Anruf-ID** ist die ID für einen Anruf. Es ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Microsoft-Support anrufen können.</li><li>**Nummerntyp** ist der Typ der Telefonnummer des Benutzers, beispielsweise ein Dienst mit gebührenfreier Nummer. </li><li>**Land oder Region** ist der Verwendungsstandort. </li> <li>**Konferenz-ID** ist die Konferenz-ID der Audio-Konferenz. </li><li>**Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Zu den Lizenztypen, die möglicherweise angezeigt werden, gehören:<ul><li>**MCOPSTNPP**: Guthaben für Kommunikationen</li><li>**MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.)</li><li>**MCOPSTN2**: Plan für Auslandsanrufe</li><li>**MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.)</li><li>**MCOPSTN6** -Domestic Calling Plan (240 min Calling Plan)</li><li>**MCOMEETADD**: Audiokonferenz</li><li>**MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung</li></ul></li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
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
|**4**   |In der Tabelle finden Sie eine Aufschlüsselung der PSTN-Nutzung pro Anruf. <ul><li>**Zeitstempel (UTC)** ist der Zeitpunkt, zu dem der Anruf gestartet wurde.</li><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln.</li><li>**SIP-Adresse** ist die SIP-Adresse des Benutzers, der den Anruf erhalten oder getätigt hat.</li><li>**Telefonnummer** ist die Nummer des Benutzers, der den Anruf getätigt hat. </li><li>**Anruftyp** ist, ob es sich bei dem Anruf um einen PSTN-Ausgangs-oder eingehenden Anruf und die Art des Anrufs, beispielsweise einen Anruf eines Benutzers oder einer Audiokonferenz, handelt. Zu den Anruftypen, die Ihnen möglicherweise angezeigt werden, gehören:<br><br>**Gruppen-Benutzer Anruftypen**<ul><li>**dr_in** – der Benutzer hat einen eingehenden PSTN-Anruf erhalten</li><li>**dr_out** – der Benutzer hat einen ausgehenden PSTN-Anruf getätigt</li><li>**dr_out_user_conf** – der Benutzer hat dem Anruf einen PSTN-Teilnehmer hinzugefügt.</li><li>**user_out_transfer** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_forwarding** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_out_user_transfer** – der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.</li><li>**dr_emergency_out** – der Benutzer führt einen Notruf durch</li></ul><br>**Anrufarten für Teams-Bots**<ul><li>**dr_in_ucap** – ein eingehender PSTN-Anruf an einen Teams-bot wie automatische Telefonzentrale oder Anrufwarteschlange</li><li>**dr_out_ucap** – ein ausgehender PSTN-Anruf von einem Teams-bot wie einer automatischen Telefonzentrale oder einer Anrufwarteschlange</li></ul><br><li>**Called to** ist die Nummer des Benutzers, der den Anruf erhalten hat.</li><li>**Startzeit (UTC)** ist der Zeitpunkt, zu dem der Anruf verbunden ist.</li><li>**Einladungs Zeit (UTC)** ist der Zeitpunkt, zu dem der Anruf initiiert wurde.</li><li>**Fehlerzeit (UTC)** ist der Zeitpunkt, zu dem der Anruf fehlgeschlagen ist. (Nur bei fehlgeschlagenen anrufen.)</li><li>**Endzeit (UTC)** ist der Zeitpunkt, zu dem der Anruf beendet wurde. (Nur für erfolgreiche Anrufe.)</li><li>**Dauer** gibt an, wie lange der Anruf verbunden war.</li><li>**Nummerntyp** ist der Typ der Telefonnummer des Benutzers, beispielsweise ein Dienst mit gebührenfreier Nummer. </li><li>**Medienumgehung** zeigt an, ob der Trunk für die medienumgehung aktiviert wurde. </li> <li>Der **SBC-FQDN** ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Session Border Controllers (SBC). </li><li>Der **Azure-Bereich** ist das für die Signalisierung verwendete Rechenzentrum.</li><li>Der **Ereignistyp** ist der Ereignistyp für den Anruf. Sie sehen Erfolg für erfolgreiche Anrufe und versuchen, fehlgeschlagene Anrufe zu führen. </li><li>Der **endgültige SIP-Code** ist der Code, mit dem der Anruf beendet wurde.</li><li>Der **endgültige Microsoft** -unter Code ist ein Code, der bestimmte Aktionen angibt, die aufgetreten sind.</li><li>**Endgültige SIP-Phrase** ist die Beschreibung des SIP-Codes und des Microsoft-Subcodes.</li><li>Die Erkennungs **-ID** ist ein eindeutiger Bezeichner für den Anruf, den Sie beim Aufrufen des Microsoft-Supports verwenden können.</li></ul> Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen.|
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Wählen Sie **Vollbild** aus, um den Bericht im Vollbildmodus anzuzeigen. |

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)