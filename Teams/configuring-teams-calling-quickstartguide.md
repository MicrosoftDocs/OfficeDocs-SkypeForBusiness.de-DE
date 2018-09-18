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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882098"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams
==============================================================

Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.

Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).

> [!NOTE]
> Wir empfehlen, bei der Planung und Umsetzung eines erfolgreichen Rollouts neben diesem Schnellstarthandbuch unsere [praktischen Anleitungen](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) und [FastTrack](https://aka.ms/cloudvoice) zu nutzen.

Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.

![Anrufe in Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams
Um die Registerkarte **Anrufe** in Microsoft Teams zu aktivieren und Ihren Benutzern das Tätigen und Empfangen von PSTN-Anrufen zu ermöglichen, müssen Sie Benutzer für das Telefonsystem und Anrufpläne bereitstellen. Eine entsprechende Anleitung finden Sie unter [Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).

## <a name="teams-interop-policy-configuration"></a>Konfiguration der Interop-Richtlinie für Microsoft Teams
Um in Microsoft Teams Anrufe empfangen zu können, müssen Sie die Upgraderichtlinie und die Interop-Richtlinie für Microsoft Teams aktualisieren. Verwenden Sie dazu das [Admin Center für Microsoft Teams und Skype for Business](https://aka.ms/teamsadmincenter) oder eine Windows PowerShell-Remotesitzung und die Skype for Business-Cmdlets [`*-CsTeamsUpgradePolicy` und `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype), um Anrufe an Microsoft Teams umzuleiten.

Weitere Informationen zur Upgraderichtlinie und zur Interop-Richtlinie für Microsoft Teams finden Sie unter [Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).

> [!TIP]
> Die benötigten PowerShell-Cmdlets finden Sie, indem Sie „CsTeamsUpgradePolicy“ oder „CsTeamsInteropPolicy“ in das Feld **Filter** in der [Dokumentation zu den PowerShell-Cmdlets für Skype for Business](https://docs.microsoft.com/powershell/module/skype) eingeben.

### <a name="default-teams-upgrade-and-interop-policies"></a>Standardmäßige Upgrade- und Interop-Richtlinien für Microsoft Teams
Microsoft Teams enthält eine Standardrichtlinienkonfiguration, die sicherstellen soll, dass vorhandene Geschäftsworkflows bei der Bereitstellung von Microsoft Teams nicht gestört werden. VoIP-, PSTN- und Partneranrufe an Ihre Benutzer werden standardmäßig weiterhin an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe in Microsoft Teams zu aktivieren. Dadurch werden unbeabsichtigte Unterbrechungen der VoIP-Dienste vermieden, wenn Sie mit dem Pilotprojekt und der Bereitstellung von Microsoft Teams beginnen.

Für die Upgraderichtlinie für Microsoft Teams wird standardmäßig der Legacymodus beibehalten. In diesem Modus wird die Interop-Richtlinie für Microsoft Teams bei der Entscheidung berücksichtigt, wohin Chats und Anrufe weitergeleitet werden sollen: zu Microsoft Teams oder zu Skype for Business.

> [!NOTE]
> Die Verhaltensweisen der Upgraderichtlinie und der Interop-Richtlinie für Microsoft Teams werden in Kürze geändert. Dies wird unter [Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) beschrieben.

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
Um eingehende PSTN-Anrufe in Microsoft Teams zu empfangen, müssen Sie Microsoft Teams als Standardanwendung für Anrufe konfigurieren. Wenden Sie dazu die Upgraderichtlinie für Microsoft Teams mit der entsprechenden Interop-Richtlinie für Microsoft Teams an, die den Parameter `CallingDefaultClient` auf „Teams“ festlegt.

> [!IMPORTANT]
> Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden. Dann können sich diese Benutzer mit den nützlichen neuen Anruffunktionen in Microsoft Teams vertraut machen, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.

Wenn Sie weiterhin die Legacyupgraderichtlinie für Microsoft Teams verwenden möchten, leiten Sie mit der folgenden vorkonfigurierten Interop-Richtlinie für Microsoft Teams eingehende PSTN-Anrufe an Microsoft Teams weiter:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Wenn Sie die aktualisierte Upgraderichtlinie für Microsoft Teams verwenden möchten, müssen Sie Ihren Benutzern den Modus „TeamsOnly“ zuweisen.

Die oben gezeigte Richtlinie legt die folgenden Verhaltensweisen fest:
* **Für bestehende Skype for Business-Kunden** leitet diese Richtlinie eingehende Anrufe an Microsoft Teams um. Dies gilt sowohl für VoIP-Anrufe (aus Microsoft Teams und Skype for Business) als auch für PSTN-Anrufe. 
* **Kunden ohne Skype for Business** empfangen, wenn die Richtlinie wirksam ist, PSTN-Anrufe in Microsoft Teams.

> [!WARNING]
> Zurzeit wirkt sich das Ändern von `CallingDefaultClient` in Microsoft Teams auch auf Anrufe an Skype for Business-IP-Telefone aus. Eingehende Anrufe werden nicht an den Telefonen empfangen und klingeln nur bei Microsoft Teams-Clients. Weitere Informationen zu vorhandenen zertifizierten SIP-Telefonen finden Sie unter [Von Skype for Business zu Microsoft Teams: Roadmap der Funktionen](https://aka.ms/skype2teamsroadmap).

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Konfigurieren von Benutzern für den Empfang von PSTN-Anrufen in Microsoft Teams
Wenn Sie die Legacyupgraderichtlinie für Microsoft Teams verwenden, wenden Sie die Interop-Richtlinie für Microsoft Teams wie oben beschrieben über eine Windows PowerShell-Remotesitzung mit Skype for Business an, um Anrufe an Microsoft Teams umzuleiten:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

Wenn Sie den Modus „TeamsOnly“ verwenden möchten, können Sie den Koexistenzmodus des Benutzers im Admin Center für Microsoft Teams und Skype for Business oder über eine Windows PowerShell-Remotesitzung mit Skype for Business in „TeamsOnly“ ändern, um Anrufe an Microsoft Teams umzuleiten:

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>Siehe auch
[Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[PowerShell-Cmdlet-Referenz für Skype for Business](https://docs.microsoft.com/powershell/module/skype)

[PowerShell-Cmdlet-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
