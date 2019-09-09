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
description: Startseite zur Bereitstellung von Cloud Voice in Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92e32950526f12c5da1856ce390ee3e532892681
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483864"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Cloud Voice in Microsoft Teams

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Sie haben möglicherweise [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md) bereitgestellt. Jetzt können Sie auch Cloud-Sprachfunktionen für Ihre Benutzer hinzufügen. 

Cloud Voice bietet Funktionen für Nebenstellanlagen (Private Branch Exchange, PBX) und Optionen für die Anbindung an das Telefonfestnetz (Public Switched Telephone Network, PSTN).

Dieser Artikel hilft Ihnen bei der Entscheidung, ob einige der Cloud Voice-Standardeinstellungen geändert werden müssen, berücksichtigt dazu das Profil und die geschäftlichen Anforderungen Ihrer Organisation und führt Sie dann schrittweise durch die einzelnen Änderungen. Wir haben die Einstellungen in zwei Gruppen aufgeteilt und beginnen mit den wichtigsten [Änderungen, die Sie mit größerer Wahrscheinlichkeit vornehmen](#core-deployment-decisions) werden. Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.

Wir empfehlen allen Organisationen, zuerst die grundlegenden Änderungen durchzuführen. Wenn Ihre Organisation zusätzliche Anforderungen hat, sehen Sie sich das folgende Material an.



## <a name="learn-more-about-cloud-voice"></a>Weitere Informationen zu Cloud Voice

In den folgenden Artikeln finden Sie weitere Informationen zur Bereitstellung und Verwendung der Cloud Voice-Features in Teams:

- [Telefonsystem in Office 365](what-is-phone-system-in-office-365.md)
- [Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)
- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Cloud Voice-Bereitstellung](cloud-voice-deployment.md)
- [Microsoft-Telefonielösungen](https://docs.microsoft.com/de-DE/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Schauen Sie sich die folgende Sitzung an, um mehr über das Telefonsystem zu erfahren: [Einführung in das Telefonsystem in Microsoft Teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).

## <a name="phone-system-office-365"></a>Telefonsystem (Office 365)

Das Telefonsystem ist die Technologie von Microsoft, die Anrufsteuerung und Funktionen von Nebenstellenanlagen (Private Branch Exchange, PBX) in der Office 365-Cloud bereitstellt. Mit dem Telefonsystem haben Sie die Möglichkeit, Ihr vorhandenes Nebenstellenanlagensystem (Private Branch Exchange, PBX) durch einen Satz von Funktionen zu ersetzen, die direkt aus Office 365 heraus bereitgestellt werden und eng in die Cloudproduktivitätserfahrungen Ihres Unternehmens integriert sind.


|Frage|Aktion |
|:------------|:-------|
|An welchen Benutzerstandorten oder in welchen Büros wird das Telefonsystem implementiert? |Weitere Informationen zum Telefonsystem finden Sie unter [Was ist das Telefonsystem in Office 365?](what-is-phone-system-in-office-365.md)</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN)

Wenn Sie das Telefonsystem mit dem Festnetz verbinden möchten, damit Benutzer in die ganze Welt Telefonanrufe tätigen können, haben Sie basierend auf Ihren geschäftlichen Anforderungen verschiedene Optionen.  Stellen Sie sich die folgenden Fragen:


|Frage|Aktion |
| :------------|:-------|
| Möchte ich den Microsoft-Anrufplan als meinen Netzbetreiber verwenden? | Weitere Informationen hierzu finden Sie unter [Telefonsystem mit Anrufplänen](calling-plan-landing-page.md).|
| Muss ich meinen bestehenden Netzbetreiber verwenden? | Weitere Informationen hierzu finden Sie unter [Telefonsystem mit direktem Routing](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Zusätzliche Bereitstellungsentscheidungen

Je nach den Anforderungen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, folgende Einstellungen zu ändern:

- Voicemail
- Anrufer-ID
- Telefonnummern von Microsoft
- Wählpläne
- Anrufwarteschleifen
- Automatische Telefonzentralen

### <a name="voicemail"></a>Voicemail

Cloud-Voicemail, unterstützt von Azure Voicemail-Diensten, unterstützt die Ablage von Voicemails nur in Exchange-Postfächern. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. Cloud-Voicemail umfasst die Voicemailaufzeichnung. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert. Möglicherweise muss Ihr Unternehmen die Voicemailaufzeichnung für bestimmte Benutzer oder für alle in der gesamten Organisation deaktivieren.

|Frage|Aktion |
|:------------|:-------|
| Möchte ich die Cloud-Voicemail aktivieren? | Das Vorgehen für die Einrichtung von Voicemail finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).
| Möchte ich die Voicemailaufzeichnung für einige oder alle meiner Benutzer aktivieren? | Wenn Sie die Aufzeichnung von Voicemails deaktivieren möchten, lesen Sie [Einrichten von Voicemailrichtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Anrufer-ID

Standardmäßig wird bei allen ausgehenden Anrufen die zugewiesene Telefonnummer als Anrufer-ID verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Frage|Aktion |
|:------------|:-------|
|Möchte ich die Anrufer-ID maskieren oder deaktivieren? | Informationen zum Ändern oder Blockieren der Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md). |
|||

### <a name="phone-numbers-from-microsoft"></a>Telefonnummern von Microsoft

Microsoft verfügt über zwei Arten von Telefonnummern: Nummern für *Abonnenten* (Benutzer), die Benutzern in Ihrer Organisation zugewiesen werden können, sowie *Dienstnummern*, die gebührenpflichtig und gebührenfrei verfügbar sind. Letztere bieten eine höhere Kapazität für gleichzeitige Anrufe als Abonnentennummern und können Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden.

|Frage|Aktion |
| :------------|:-------|
| Welche Benutzerstandorte benötigen neue Telefonnummern von Microsoft? | Informationen zum Abrufen neuer Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) und [Reservieren von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md). 
| Welche Art von Telefonnummer (Abonnenten oder Dienst) benötige ich? | Informationen, wie Sie die Art der Telefonnummer auswählen, die Sie benötigen, finden Sie unter [Unterschiedliche Arten von Telefonnummern für Anrufpläne](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Wie kann ich vorhandene Telefonnummern nach Office 365 übertragen?|Weitere Informationen finden Sie unter [Übertragen von Telefonnummern nach Office 365](transfer-phone-numbers-to-office-365.md).
|||

### <a name="dial-plans"></a>Wählpläne

Bei einem Wählplan in der Telefonsystemfunktion von Office 365 handelt es sich um eine Gruppe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise das Format E.164) übersetzt, um Anrufe zu autorisieren und weiterzuleiten.

Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation einen angepassten Wählplan? | Um zu ermitteln, ob Sie einen angepassten Wählplan benötigen, sehen Sie sich den Abschnitt [Planen eines Mandantenwählplans](what-are-dial-plans.md#planning-for-tenant-dial-plans) an.|
Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden? | Wenn Sie Benutzer mithilfe von PowerShell zu einem benutzerdefinierten Wählplan hinzufügen möchten, lesen Sie den Abschnitt [Erstellen und Verwalten von Wahlplänen](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Anrufwarteschleifen

Cloudanrufwarteschleifen beinhalten die telefonischen Begrüßungen Ihrer Organisation sowie die Möglichkeit, den Anruf automatisch zu halten und nach dem nächsten verfügbaren Ansprechpartner zu suchen, während für den Anrufer Musik abgespielt wird. Sie können eine oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen. 


|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation Anrufwarteschleifen? | Weitere Informationen hierzu finden Sie unter [Erstellen einer Cloudanrufwarteschleife](https://docs.microsoft.com/de-DE/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) und [Einrichten des Telefonsystems](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Automatische Telefonzentralen

Sie können automatische Telefonzentralen verwenden, um ein Menüsystem für Ihre Organisation zu erstellen. Dann können externe und interne Anrufer durch das Menüsystem navigieren, um Benutzer in der Firma oder Abteilungen in der Organisation zu finden und sie anzurufen oder Anrufe an sie durchzustellen.

|Frage|Aktion |
|:------------|:-------|
| Benötigt meine Organisation automatische Telefonzentralen? | Weitere Informationen finden Sie unter [Was sind automatische Cloudtelefonzentralen](what-are-phone-system-auto-attendants.md) und [Einrichten einer automatischen Cloudtelefonzentrale](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Geräte

Weitere Informationen zu unterstützten Geräten finden Sie in den folgenden Themen:

- [Verwalten Ihrer Geräte in Microsoft Teams](device-management.md)
- [IP-Telefone](https://docs.microsoft.com/de-DE/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB-Audio- und -Videogeräte](https://docs.microsoft.com/de-DE/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Intelligente Kommunikation für Geräte](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


