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
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Erfahren Sie mehr über die Cloud-VoIP-Funktion, und verstehen Sie die erforderlichen Bereitstellungsentscheidungen, denen Sie gegenüberstehen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a05ba72f52d4131229b28072a615bf12f6b5930
ms.sourcegitcommit: 491c44b6a9b30faaf4d73394969f4a0587362830
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "47820499"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a>VoIP-Telefon System-und PSTN-Verbindungsoptionen

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleichthaben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Jetzt sind Sie bereit, Ihren Benutzern Sprachfunktionen hinzuzufügen. 

Voice bietet Funktionen für Private Branch Exchange (PBX) und Optionen zum Herstellen einer Verbindung mit dem öffentlich geschalteten Telefonnetz (PSTN).

Dieser Artikel hilft Ihnen bei der Entscheidung, ob Sie die standardmäßigen Spracheinstellungen basierend auf den Profil-und Geschäftsanforderungen Ihrer Organisation ändern müssen, und führt Sie durch die einzelnen Änderungen. Wir haben die Einstellungen in zwei Gruppen aufgeteilt, beginnend mit dem Haupt Satz von [Änderungen, die Sie wahrscheinlicher vornehmen werden](#core-deployment-decisions). Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.

Wir empfehlen, dass alle Organisationen die grundlegenden Entscheidungen treffen, und wenn Ihre Organisation zusätzliche Anforderungen hat, überprüfen Sie das folgende Material.

 > [!Note]
> Details zu den Telefonsystem Funktionen auf unterschiedlichen Plattformen finden Sie unter [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="learn-more-about-voice"></a>Weitere Informationen zu Voice

In den folgenden Artikeln finden Sie weitere Informationen zum Bereitstellen und Verwenden von Sprachfeatures in Teams:

- [Telefon System in Microsoft 365 oder Office 365](what-is-phone-system-in-office-365.md)
- [Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)
- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Microsoft-Telefonielösungen](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Schauen Sie sich die folgende Sitzung an, um mehr über das Telefonsystem zu erfahren: [Einführung in das Telefonsystem in Microsoft Teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).

## <a name="phone-system-office-365"></a>Telefon System (Office 365)

Telefon System ist die Microsoft-Technologie für die Aktivierung der Anrufsteuerung und der Funktionen für Private Branch Exchange (PBX) in der Microsoft 365-oder Office 365-Cloud. Mit dem Telefonsystem können Sie Ihr vorhandenes Private Branch Exchange (PBX)-System durch eine Reihe von Features ersetzen, die direkt von Microsoft 365 oder Office 365 bereitgestellt und eng in die Cloud-Produktivitäts Erfahrung des Unternehmens integriert sind.


|Frage|Aktion |
|:------------|:-------|
|An welchen Speicherorten oder Büros wird das Telefon System implementiert? |Weitere Informationen zum Telefonsystem finden Sie unter [Was ist Telefonsystem in Microsoft 365 oder Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
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

Microsoft hat zwei Arten von Telefonnummern zur Verfügung: *Teilnehmer* (Benutzer) Nummern, die Benutzern in Ihrer Organisation zugewiesen werden können, und *Dienst* Nummern, die als gebührenpflichtige und gebührenfreie Servicenummern zur Verfügung stehen, die eine höhere gleichzeitige Anrufkapazität als Teilnehmer Nummern aufweisen und Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden können.

|Frage|Aktion |
| :------------|:-------|
| Welche Benutzer Standorte benötigen neue Telefonnummern von Microsoft? | Informationen zum Abrufen von Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md). 
| Welche Art von Telefonnummer (Abonnent oder Dienst) benötige ich? | Wenn Sie die Art der benötigten Telefonnummer ermitteln möchten, finden Sie unter [verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md)werden.
Wie kann ich vorhandene Telefonnummern an Teams portieren?|Weitere Informationen finden Sie unter [übertragen von Telefonnummern an Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
|||

### <a name="dial-plans"></a>Wählpläne

Ein Wählplan in der Telefon System Funktion von Microsoft 365 oder Office 365 ist eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzen.

Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation einen angepassten Wählplan? | Informationen zum ermitteln, ob Sie einen benutzerdefinierten Wählplan benötigen, finden Sie unter [Planen von Mandanten Wählplänen](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden? | Informationen zum Hinzufügen von Benutzern zu einem benutzerdefinierten Wählplan in PowerShell finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Anrufwarteschleifen

Cloudanrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Telefonisten zu suchen, um den Anruf zu entgegenzunehmen, während die Anrufe gehalten werden und die Anrufer dabei Musik hören. Sie können einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen. 


|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation Anrufwarteschlangen? | Weitere Informationen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten Ihres Telefonsystems](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Automatische Telefonzentralen

Sie können automatische Telefonzentralenverwenden, um ein Menüsystem für Ihre Organisation zu erstellen. Dann können externe und interne Anrufer durch das Menüsystem navigieren, um Benutzer in der Firma oder Abteilungen in der Organisation zu finden und sie anzurufen oder Anrufe an sie durchzustellen.

|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation automatische Telefonzentralen? | Weitere Informationen finden Sie unter [Was sind automatische Cloud-Telefonzentralen](what-are-phone-system-auto-attendants.md) und [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Geräte

Weitere Informationen zu unterstützten Geräten finden Sie unter den folgenden Themen:

- [Verwalten Ihrer Geräte in Microsoft Teams](devices/device-management.md)
- [IP-Telefone](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB-Audio- und -Videogeräte](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Intelligente Kommunikation für Geräte](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


