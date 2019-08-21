---
title: Cloud Voice in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
search.appverid: MET150
description: Startseite zum Bereitstellen von Cloud-VoIP in Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92e32950526f12c5da1856ce390ee3e532892681
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483864"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Cloud Voice in Microsoft Teams

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleichthaben Sie [Besprechungen #a0 Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Nun können Sie Ihren Benutzern Cloud-Sprachfunktionen hinzufügen. 

Cloud Voice bietet Funktionen für Private Branch Exchange (PBX) und Optionen zum Herstellen einer Verbindung mit dem öffentlich geschalteten Telefonnetz (PSTN).

Dieser Artikel hilft Ihnen bei der Entscheidung, ob Sie die Standardeinstellungen für die Cloud-VoIP basierend auf den Profil-und Geschäftsanforderungen Ihrer Organisation ändern müssen, und führt Sie durch die einzelnen Änderungen. Wir haben die Einstellungen in zwei Gruppen aufgeteilt, beginnend mit dem Haupt Satz von [Änderungen, die Sie wahrscheinlicher vornehmen werden](#core-deployment-decisions). Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.

Wir empfehlen, dass alle Organisationen die grundlegenden Entscheidungen treffen, und wenn Ihre Organisation zusätzliche Anforderungen hat, überprüfen Sie das folgende Material.



## <a name="learn-more-about-cloud-voice"></a>Weitere Informationen zu Cloud-VoIP

In den folgenden Artikeln finden Sie weitere Informationen zur Bereitstellung und Verwendung von Cloud-Sprachfeatures in Teams:

- [Telefonsystem in Office 365](what-is-phone-system-in-office-365.md)
- [Telefon System mit Anrufplänen](calling-plan-landing-page.md)
- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Cloud Voice-Bereitstellung](cloud-voice-deployment.md)
- [Microsoft-Telefonielösungen](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Schauen Sie sich die folgende Sitzung an, um mehr über das Telefonsystem zu erfahren: [Einführung in das Telefonsystem in Microsoft Teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).

## <a name="phone-system-office-365"></a>Telefon System (Office 365)

Telefon System ist die Microsoft-Technologie für die Aktivierung der Anrufsteuerung und der Funktionen für Private Branch Exchange (PBX) in der Office 365-Cloud. Mit dem Telefonsystem können Sie Ihr vorhandenes Private Branch Exchange (PBX)-System durch eine Reihe von Features ersetzen, die direkt von Office 365 bereitgestellt werden und eng in die Cloud-Produktivitäts Erfahrung des Unternehmens integriert sind.


|Frage|Aktion |
|:------------|:-------|
|An welchen Speicherorten oder Büros wird das Telefon System implementiert? |Weitere Informationen zum Telefonsystem finden Sie unter [Was ist Telefonsystem in Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Verbindung mit dem öffentlich geschalteten Telefonnetz (PSTN)

Wenn Sie das Telefon System mit dem öffentlichen Telefonnetz (PSTN) verbinden möchten, damit Benutzer überall in der Welt Telefonanrufe tätigen können, haben Sie Optionen, die auf Ihren geschäftlichen Anforderungen basieren.  Stellen Sie sich folgende Fragen:


|Frage|Aktion |
| :------------|:-------|
| Möchte ich den Microsoft-Anrufplan als meinen Telefonnetzbetreiber verwenden? | Weitere Informationen finden Sie unter [Telefon System mit Anrufplänen](calling-plan-landing-page.md).|
| Muss ich meinen eigenen Telefonnetzbetreiber verwenden? | Weitere Informationen finden Sie unter [Telefon System mit direktem Routing](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Zusätzliche Bereitstellungsentscheidungen

Basierend auf den Anforderungen und der Konfiguration Ihrer Organisation können Sie die Einstellungen für Folgendes ändern:

- Voicemail
- Identität des Anrufs
- Telefonnummern von Microsoft
- Wählpläne
- Anrufwarteschleifen
- Automatische Telefonzentralen

### <a name="voicemail"></a>Voicemail

Cloud Voicemail, powered by Azure Voicemail Services, unterstützt Voicemail-Einzahlungen nur für Exchange-Postfächer und unterstützt keine e-Mail-Systeme von Drittanbietern. Cloud Voicemail umfasst Voicemail-Transkription, die standardmäßig für alle Benutzer in Ihrer Organisation aktiviert ist. Für Ihre geschäftlichen Anforderungen müssen Sie möglicherweise die Voicemail-Transkription für bestimmte Benutzer oder alle in der Organisation deaktivieren.

|Frage|Aktion |
|:------------|:-------|
| Möchte ich Cloud Voicemail aktivieren? | Anweisungen zum Einrichten von Voicemail finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).
| Soll die Sprachübertragung für einige oder alle meine Benutzer aktiviert werden? | Informationen zum Deaktivieren der Voicemail-Transkription finden Sie unter [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Identität des Anrufs

Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anruf Identität (Rufnummernanzeige). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Frage|Aktion |
|:------------|:-------|
|Soll die Rufnummernanzeige maskiert oder deaktiviert werden? | Informationen zum Ändern oder Blockieren der Rufnummernanzeige finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md). |
|||

### <a name="phone-numbers-from-microsoft"></a>Telefonnummern von Microsoft

Microsoft hat zwei Arten von Telefonnummern zur Verfügung: *Teilnehmer* (Benutzer) Nummern, die Benutzern in Ihrer Organisation zugewiesen werden können, und *Dienst* Nummern, die als gebührenpflichtige und gebührenfreie Servicenummern zur Verfügung stehen, die einen höheren gleichzeitigen Anruf haben Kapazität als Abonnenten Nummern und können Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden.

|Frage|Aktion |
| :------------|:-------|
| Welche Benutzer Standorte benötigen neue Telefonnummern von Microsoft? | Informationen zum Abrufen von Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md). 
| Welche Art von Telefonnummer (Abonnent oder Dienst) benötige ich? | Wenn Sie die Art der benötigten Telefonnummer ermitteln möchten, finden Sie unter [verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md)werden.
Wie kann ich vorhandene Telefonnummern nach Office 365 portieren?|Weitere Informationen finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
|||

### <a name="dial-plans"></a>Wählpläne

Ein Wählplan in der Telefon System Funktion von Office 365 ist eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzen.

Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation einen angepassten Wählplan? | Informationen zum ermitteln, ob Sie einen benutzerdefinierten Wählplan benötigen, finden Sie unter [Planen von Mandanten Wählplänen](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden? | Informationen zum Hinzufügen von Benutzern zu einem benutzerdefinierten Wählplan in PowerShell finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Anrufwarteschleifen

Zu den Cloud-Anrufwarteschlangen gehören Begrüßungen, die verwendet werden, wenn sich jemand an eine Telefonnummer für Ihre Organisation anmeldet, die Möglichkeit, die Anrufe automatisch zu halten, und die Möglichkeit, nach dem nächsten verfügbaren Anruf Agenten zu suchen, um den Anruf zu führen, während die Anrufteilnehmer Musik hören in Wartestellung. Sie können eine oder mehrere Anrufwarteschlangen für Ihre Organisation erstellen. 


|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation Anrufwarteschlangen? | Weitere Informationen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten Ihres Telefonsystems](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Automatische Telefonzentralen

Automatische Cloud-Telefonzentralen können zum Erstellen eines Menüsystems für Ihre Organisation verwendet werden, mit dem externe und interne Anrufer über ein Menü System navigieren können, um Anrufe an Unternehmensbenutzer oder Abteilungen in Ihrer Organisation zu suchen und dort zu platzieren oder zu übertragen.

|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation automatische Telefonzentralen? | Weitere Informationen finden Sie unter [Was sind automatische Cloud-Telefonzentralen](what-are-phone-system-auto-attendants.md) und [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Geräte

Weitere Informationen zu unterstützten Geräten finden Sie unter den folgenden Themen:

- [Verwalten Ihrer Geräte in Microsoft Teams](device-management.md)
- [IP-Telefone](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB-Audio- und -Videogeräte](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Intelligente Kommunikation für Geräte](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


