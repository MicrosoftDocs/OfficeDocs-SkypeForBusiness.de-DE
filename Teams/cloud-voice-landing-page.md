---
title: Cloud Voice in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Zielseite für die Bereitstellung von Cloud-VoIP in Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: abc8d3e552820ee93b5ccd1fc968e914ac5287ba
ms.sourcegitcommit: 4e750efd107dfc9bfd8b09d64abd40e0e27734de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "30948377"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Cloud Voice in Microsoft Teams

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Sie können nun Cloud Voice-Funktionen für Ihre Benutzer hinzufügen. 

Cloud-VoIP bietet Funktionen für (Private Branch Exchange, PBX) und Optionen für die Verbindung zu im Public Switched Telephone Network, (PSTN).

In diesem Artikel Unterstützung bei der Entscheidung, ob Sie die Cloud VoIP Standardeinstellungen, basierend auf Ihrer Organisation Profil und geschäftlichen Anforderungen, und klicken Sie dann Sie über jede Änderung geführt ändern müssen. Wir haben die Einstellungen in zwei Gruppen, beginnend mit der Kerngruppe von [Änderungen, die Sie eher Stellen sind](#core-deployment-decisions)aufgeteilt. Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.

Es wird empfohlen, dass alle Organisationen über den Core Entscheidungen arbeiten, und Sie, wenn Ihre Organisation zusätzliche Anforderungen umfasst das folgenden Material überprüfen.



## <a name="learn-more-about-cloud-voice"></a>Erfahren Sie mehr über Cloud-VoIP

Die folgenden Artikel enthalten weitere Informationen zum Bereitstellen und Verwenden von Cloud-VoIP-Funktionen in Teams:

- [Telefonsystem in Office 365](what-is-phone-system-in-office-365.md)
- [Telefonsystem mit dem Aufrufen der Pläne](calling-plan-landing-page.md)
- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Cloud Voice-Bereitstellung](cloud-voice-deployment.md)
- [Microsoft-Telefonielösungen](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Die folgenden Sitzung Weitere Informationen zum Telefonsystem Video: [Einführung in das Telefonsystem in Microsoft-Teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).

## <a name="phone-system-office-365"></a>Telefonsystem (Office 365)

Telefonsystem ist Microsoft Technologie zum Aktivieren der Remote Call Control und Funktionen in der Office 365-Cloud (Private Branch Exchange, PBX). Telefonsystem können Sie das bestehende System (Private Branch Exchange, PBX) durch eine Reihe von Features von Office 365 direkt bereitgestellt und eng integriert in das Unternehmen produktivitätserfahrung der Cloud zu ersetzen.


|Frage|Aktion |
|:------------|:-------|
|In welche Standorte oder Büros implementieren ich Telefonsystem? |Weitere Informationen zu Telefonsystem finden Sie unter [Was ist Telefonsystem in Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Verbindung mit der Public Switched Telephone Telefonnetz (PSTN)

Um das Telefonsystem zu im Public Switched Telephone Network, (PSTN) anschließen, damit die Benutzer auf der ganzen Welt Telefonanrufe tätigen können, müssen Sie basierte auf Ihrer geschäftlicher Bedarf Optionen.  Stellen Sie sich Folgendes:


|Frage|Aktion |
| :------------|:-------|
| Führen Sie ich möchte Microsoft aufrufen planen als meines Telefonie verwenden? | Weitere Informationen finden Sie unter [Telefonsystem mit plant aufrufen](calling-plan-landing-page.md).|
| Benötige ich meinen eigenen Telefonie Netzbetreiber verwenden? | Weitere Informationen finden Sie unter [Telefonsystem mit direktem Routing](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Zusätzliche Bereitstellungsentscheidungen

Sie möchten die Einstellungen für den folgenden ändern basierend auf Ihrer Organisation Anforderungen und Konfiguration:

- Voicemail
- Aufrufen von Identität
- Telefonnummern von Microsoft.
- Wählpläne
- Anrufwarteschleifen
- Automatische Telefonzentralen

### <a name="voicemail"></a>Voicemail

Cloud-Voicemail, unterstützt von Azure Voicemail-Dienste unterstützt Voicemail bandbreitenbeschränkungen zu nur Exchange-Postfächern und Drittanbieter-e-Mail-Systemen nicht unterstützt. Cloud-Voicemail enthält Voicemail Lautschrift, die standardmäßig für alle Benutzer in Ihrer Organisation aktiviert ist. Ihre geschäftsanforderungen erfordern möglicherweise, Voicemail Lautschrift für bestimmte Benutzer oder alle Benutzer in der gesamten Organisation zu deaktivieren.

|Frage|Aktion |
|:------------|:-------|
| Möchte ich Cloud Voicemail aktivieren? | Voicemail-Setup-Verfahren finden Sie unter [Einrichten von Voicemail Cloud](set-up-phone-system-voicemail.md).
| Möchte ich Voicemail Lautschrift für einige oder alle Benutzer aktivieren? | Um Voicemail Lautschrift deaktivieren, finden Sie unter [Festlegen von Voicemail Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Aufrufen von Identität

Alle ausgehenden Anrufe verwenden standardmäßig die zugewiesene Telefonnummer als aufrufende Identität (Anrufer-ID). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Frage|Aktion |
|:------------|:-------|
|Soll so aktivieren oder Deaktivieren der Anrufer-ID werden? | Ändern oder die Anrufer-ID zu blockieren, finden Sie unter [Legen Sie die Anrufer-ID für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||

### <a name="phone-numbers-from-microsoft"></a>Telefonnummern von Microsoft.

Microsoft verfügt über zwei Arten von Telefonnummern zur Verfügung: *Abonnenten* (Benutzer) Zahlen, die Benutzer in Ihrer Organisation zugewiesen werden können, und *Service* Zahlen als gebührenpflichtige oder gebührenfreie Service Numbers höheren gleichzeitige angerufen werden verfügbar Kapazität als Abonnenten Zahlen und Diensten wie etwa Audiokonferenzen, automatischen Telefonzentralen oder rufen Sie Warteschlangen zugewiesen werden können.

|Frage|Aktion |
| :------------|:-------|
| Welche Benutzerstandorte benötigen Sie neue Telefonnummern von Microsoft? | Informationen zum Abrufen von Telefonnummern finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Abrufen von Telefonnummern für Ihre Benutzer](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users). 
| Der Typ der Telefonnummer (Abonnenten oder Dienst) benötige ich? | Zur einfacheren wählen Sie den Typ der Telefonnummer, die Sie benötigen, finden Sie unter [verschiedenen Arten von Telefonnummern für den Aufruf von plant verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Wie kann ich vorhandene Rufnummern Port zu Office 365?|Weitere Informationen finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
|||

### <a name="dial-plans"></a>Wählpläne

Ein Wählplan in das Telefonsystem Feature von Office 365 ist, dass eine Reihe von Normalisierungsregeln, die Übersetzen von Telefonnummern in ein anderes Format (normalerweise e. 164-Format) für Anrufberechtigungen und Anrufrouting gewählt.

Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation einen angepassten Wählplan? | Um zu bestimmen, wenn Sie einen benutzerdefinierten Wählplan benötigen, finden Sie unter [Planen Mandanten Wählpläne](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden? | Zum Hinzufügen von Benutzern zu einem benutzerdefinierten Wählplan in PowerShell finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Anrufwarteschleifen

System-Telefonanruf Warteschlangen enthalten Ansage, die verwendet werden, wenn angerufen eine Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und für den nächsten verfügbaren Anruf-Agent zum Verarbeiten des Anrufs beim Personen die Möglichkeit zum Suchen, die Anruf Musik in der Warteschleife hören sind. Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen. 


|Frage|Aktion |
|:------------|:-------|
| Ruft meiner Organisation Warteschlangen auf müssen? | Weitere Informationen finden Sie unter [erstellen eine Telefonsystem Anruf Warteschlange](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten von Ihrem Telefonsystem](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Automatische Telefonzentralen

Telefonsystem Telefonzentralen verwendet werden können, um ein Menüsystem für Ihre Organisation zu erstellen, externe und interne Anrufer können, über ein Menüsystem platzieren, und durchstellen von Anrufen an Unternehmen Benutzer oder Abteilungen in Ihrer Organisation verschieben.

|Frage|Aktion |
|:------------|:-------|
| Werden meine Organisation für automatische Telefonzentralen benötigt? | Weitere Informationen finden Sie unter [Was sind Telefonsystem automatischen Telefonzentralen](what-are-phone-system-auto-attendants.md) und [Richten Sie eine automatische Telefonzentrale Telefonsystem](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). |

### <a name="devices"></a>Geräte

Weitere Informationen zu den unterstützten Geräten finden Sie unter den folgenden:

- [Verwalten Ihrer Geräte in Microsoft Teams](device-management.md)
- [IP-Telefone](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB-Audio- und -Videogeräte](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Intelligente Communications für Geräte](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


