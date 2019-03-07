---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1d2fd7a9b999d98109e732b3bdbbba16f26e3bf
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460572"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams
==============================================================

Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.

Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).

> [!NOTE]
> Es wird empfohlen, die gleichzeitig mit diesem Schnellstart-Handbuch, lesen Sie die [Telefonsystem mit Aufrufen plant](calling-plan-landing-page.md) und [schnelle](https://aka.ms/cloudvoice) zur Planung und Laufwerk eine erfolgreiche Einführung.

Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.

![Anrufe in Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams
Zum Aktivieren der Registerkarte **Anrufe** in Teams benötigen Benutzer 1:1 aktiviert werden, Teams aufrufen und Verwenden von Clientidentität Teams, die 1:1-Teams aufrufen unterstützt. Weitere Informationen zum Verwalten von 1:1 einwählen, Teams lesen Sie [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Um zu erfahren, welche Clients aufrufen unterstützen, lesen Sie [Grenzwerte und Spezifikationen für Microsoft-Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Derzeit wird Voicemail in der Registerkarte Anrufe nicht verfügbar, wenn der Benutzer für PSTN-Anrufe aktiviert ist. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Voraussetzungen für das **Wähltastenfeld** im Teams aktivieren
Zum Aktivieren der Registerkarte **Wähltastatur** in Teams und ermöglichen die Benutzer das tätigen und annehmen von PSTN-Anrufe müssen Sie die Bereitstellung von Benutzern für Telefonsystem und plant aufrufen. Zum Aufrufen von plant einrichten finden Sie unter [Einrichten von plant aufrufen](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Sie können auch direkten Routing zulassen, dass Ihre Benutzer zu Erf und PSTN-Anrufe empfangen. Weitere Informationen zum Einrichten der direkten Routing lesen Sie [Direkten Routing konfigurieren](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).

## <a name="teams-interop-policy-configuration"></a>Konfiguration der Interop-Richtlinie für Microsoft Teams
Um Teams beginnen annehmen von Anrufen zu aktivieren, müssen Sie Upgrade Teams und Teams Interop-Richtlinie, Aktualisieren über [Microsoft-Teams-Verwaltungskonsole](https://aka.ms/teamsadmincenter) oder mithilfe von remote Windows PowerShell-Sitzung mit dem Skype für Business [ `*-CsTeamsUpgradePolicy` und `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) Cmdlets zum Umleiten von Anrufen an Teams.

Weitere Informationen zu Upgrades Teams und Teams Interop-Richtlinie finden Sie unter [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Um den PowerShell-Cmdlets zu suchen, die Sie benötigen, geben Sie "CsTeamsUpgradePolicy" oder "CsTeamsInteropPolicy" im Feld **Filter** in der [Skype für Business PowerShell-Cmdlet-Dokumentation](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-upgrade-and-interop-policies"></a>Standard-Teams Upgrade und Interop-Richtlinien
Microsoft Teams enthält eine Standardrichtlinienkonfiguration, die sicherstellen soll, dass vorhandene Geschäftsworkflows bei der Bereitstellung von Microsoft Teams nicht gestört werden. VoIP-, PSTN- und Partneranrufe an Ihre Benutzer werden standardmäßig weiterhin an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe in Microsoft Teams zu aktivieren. Dadurch werden unbeabsichtigte Unterbrechungen der VoIP-Dienste vermieden, wenn Sie mit dem Pilotprojekt und der Bereitstellung von Microsoft Teams beginnen.

Upgrade Richtlinie in der Standardeinstellung ist bei legacy-Modus, die berücksichtigt werden Teams Interop-Richtlinie, um festzustellen, wo Chats und Anrufe weitergeleitet werden – stehen aufbewahrt Teams Teams oder Skype für Unternehmen.

> [!NOTE]
> Die Verhalten des Teams aktualisieren Richtlinie und Teams Interop-Richtlinie wird bald ändern, wie beschrieben in [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

So sieht die Standardkonfiguration der Interop-Richtlinie für Microsoft Teams aus:

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Die Standardkonfiguration sieht die folgenden Verhaltensweisen vor:
* **Für bestehende Skype for Business-Kunden** soll die Richtlinie sicherstellen, dass Skype for Business-Anrufe an Skype for Business und Microsoft Teams-Anrufe an Microsoft Teams geleitet werden. PSTN-Anrufe und Partneranrufe werden an Skype for Business geleitet, wenn diese Richtlinie wirksam ist.
* **Für Kunden ohne Skype for Business** sind, wenn die Richtlinie wirksam ist, zusätzlich zu den Anrufen zwischen Microsoft Teams-Benutzern nur ausgehende PSTN-Anrufe in Microsoft Teams verfügbar. Sie müssen die Ihren Benutzern zugewiesene Interop-Richtlinie für Microsoft Teams ändern, damit PSTN-Anrufe in Microsoft Teams empfangen werden können.

> [!NOTE]
> Für Benutzer, für die Telefonsystem- und Anrufplanlizenzen zur Verwendung mit Skype for Business Online bereitgestellt sind und für die die standardmäßige globale Interop-Richtlinie für Microsoft Teams konfiguriert ist, gilt Folgendes. Die Registerkarte „Anrufe“ in Microsoft Teams ist aktiviert, und sie können ausgehende PSTN-Anrufe tätigen, ohne dass Administratoren tätig werden müssen.

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Konfigurieren von Microsoft Teams für den Empfang von eingehenden PSTN-Anrufen
Wenn in Teams eingehende PSTN-Anrufe annehmen möchten, müssen Sie Teams als Standardgerät für Anrufe Anwendung durch die Anwendung Teams Upgrade Gruppenrichtlinien mit der entsprechenden Teams Interop-Richtlinie, die festlegt konfigurieren `CallingDefaultClient` Parameter Teams.

> [!IMPORTANT]
> Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden. Dann können sich diese Benutzer mit den nützlichen neuen Anruffunktionen in Microsoft Teams vertraut machen, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.

Wenn Sie weiterhin der Richtlinie der Vorversion Upgrade Teams verwenden auswählen, verwenden Sie die folgenden vorkonfigurierte Teams Interop-Richtlinie eingehenden PSTN-Anrufe zu Teams weiterleiten:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Wenn Sie die aktualisierte Teams Richtlinie Upgrade verwenden, müssen Sie Teams nur Kopfzeilen herunterladen, die Benutzern zugewiesen.

Die oben gezeigte Richtlinie legt die folgenden Verhaltensweisen fest:
* **Für bestehende Skype for Business-Kunden** leitet diese Richtlinie eingehende Anrufe an Microsoft Teams um. Dies gilt sowohl für VoIP-Anrufe (aus Microsoft Teams und Skype for Business) als auch für PSTN-Anrufe. 
* **Kunden ohne Skype for Business** empfangen, wenn die Richtlinie wirksam ist, PSTN-Anrufe in Microsoft Teams.

> [!WARNING]
> Zurzeit wirkt sich das Ändern von `CallingDefaultClient` in Microsoft Teams auch auf Anrufe an Skype for Business-IP-Telefone aus. Eingehende Anrufe werden nicht an den Telefonen empfangen und klingeln nur bei Microsoft Teams-Clients. Informationen zur Unterstützung von vorhandenen zertifizierten SIP-Telefone finden Sie in der [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap) .

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Zum Konfigurieren von Benutzern Empfang von PSTN-Anrufe in Teams
Bei Verwendung der Richtlinie der Vorversion Upgrade Teams gelten Sie die Teams Interop-Richtlinie wie oben über Skype für Business remote Windows PowerShell-Sitzung zum Umleiten von Anrufen an Teams beschrieben:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Wenn Sie entscheiden, nur Teams Modus verwenden, können Sie die Benutzermodus Koexistenz Teams nur über das Microsoft-Teams Acmin Center oder über einen Skype für Business remote Windows PowerShell-Sitzung zum Umleiten von Anrufen an Teams ändern:

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Siehe auch
[Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)

[PowerShell-Cmdlet-Referenz für Skype for Business](https://docs.microsoft.com/powershell/module/skype)

[PowerShell-Cmdlet-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
