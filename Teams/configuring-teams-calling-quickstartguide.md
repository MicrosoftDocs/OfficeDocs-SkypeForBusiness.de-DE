---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Schnellstarthandbuch zum Konfigurieren von Anrufplänen in Microsoft Teams, damit Sie einen Satz von Benutzern einrichten und ausführen können.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789580"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams

Dieser Leitfaden hilft Ihnen, eine Reihe von Benutzern einzurichten, damit sie Anrufpläne in Teams erkunden können.

Lesen Sie die Ankündigung von Anrufplänen in Teams vom 12. Dezember 2017: [Intelligente Kommunikation macht den nächsten Schritt mit Anrufen in Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Wir empfehlen, parallel zu diesem Schnellstarthandbuch das [Telefonsystem mit Anrufplänen](calling-plan-landing-page.md) und [FastTrack](https://aka.ms/cloudvoice) zu lesen, um ein erfolgreiches Rollout zu planen und voranzutreiben.

Durch Hinzufügen von Anrufplänen – einem Microsoft 365- und Office 365-Feature, das von Skype for Business unterstützt wird – können Sie jetzt Teams verwenden, um Telefonanrufe an oder von Landleitungen und Mobiltelefonen über das Festnetz (Public Switched Telephone Network, PSTN) zu tätigen und zu empfangen.

![Screenshot der Seite "Kontakte" in Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Voraussetzungen für die Aktivierung der Registerkarte **"Anrufe** " in Teams
Um die Registerkarte **"Anrufe** " in Teams zu aktivieren, müssen Benutzer 1:1-Anrufe in Teams aktiviert haben und einen Teams-Client verwenden, der 1:1-Teams-Anrufe unterstützt. Informationen zum Verwalten von 1:1-Anrufen in Teams finden Sie unter [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Um zu erfahren, welche Clients Anrufe unterstützen, lesen Sie bitte [Die Grenzwerte und Spezifikationen für Microsoft Teams](./limits-specifications-teams.md).

> [!NOTE]
> Derzeit ist Voicemail auf der Registerkarte "Anrufe" nur verfügbar, wenn der Benutzer für PSTN-Anrufe aktiviert ist. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Voraussetzungen für die Aktivierung der **Wähltastatur** in Teams
Um die Registerkarte " **Wähltastatur** " in Teams zu aktivieren und Ihren Benutzern das Tätigen und Empfangen von PSTN-Anrufen zu ermöglichen, müssen Sie Benutzer für Telefonsystem- und Anrufpläne bereitstellen. Informationen zum Einrichten von Anrufplänen finden Sie unter ["Einrichten von Anrufplänen"](./set-up-calling-plans.md).
Darüber hinaus müssen Sie für Teams-Benutzer sicherstellen, dass "Private Anrufe zulassen" in der Teams-Anrufrichtlinie aktiviert ist. Weitere Informationen finden [Sie unter Verwalten von Teams während des Übergangs zum neuen Microsoft Teams Admin Center](./manage-teams-skypeforbusiness-admin-center.md) .
> [!NOTE]
> Sie können auch Direct Routing verwenden, um Ihren Benutzern das Tätigen und Empfangen von PSTN-Anrufen zu ermöglichen. Informationen zum Einrichten von Direct Routing finden Sie unter [Konfigurieren von Direct Routing](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Verwenden von TeamsUpgradePolicy zum Steuern, wo Anrufe landen
Um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype for Business landen, verwenden Administratoren TeamsUpgradePolicy, entweder über das [Microsoft Teams Admin Center](https://aka.ms/teamsadmincenter) oder über eine Remote-Windows PowerShell-Sitzung mit den Skype for Business-Cmdlets.[](/powershell/module/skype)


Die Standardkonfiguration von TeamsUpgradePolicy ist der Inselmodus, der sicherstellen soll, dass vorhandene Geschäftsworkflows während einer Teams-Bereitstellung nicht unterbrochen werden. VoIP-, PSTN- und Verbundanrufe an Ihre Benutzer werden standardmäßig weiterhin an Skype for Business weitergeleitet, bis Sie die Richtlinie so aktualisieren, dass eingehende Anrufe an Teams aktiviert werden.  Wenn sich Empfänger im Inselmodus befinden:

 - Eingehende VOIP-Anrufe, die von Skype for Business stammen, landen immer im Skype for Business Client des Empfängers.
 - Eingehende VOIP-Anrufe, die in Teams getätigt wurden, landen in Teams, *wenn sich Der Absender und Empfänger im selben Mandanten befinden*.
 - Eingehende Verbund-VOIP-Anrufe (unabhängig davon, welcher Client stammt) und PSTN-Anrufe landen immer im Skype for Business Client des Empfängers.
 
Um sicherzustellen, dass eingehende VOIP- und PSTN-Anrufe immer im Teams-Client eines Benutzers landen, aktualisieren Sie den Koexistenzmodus des Benutzers auf "TeamsOnly" (d. h. weisen Sie ihm die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.  Weitere Informationen zu Koexistenzmodi und TeamsUpgradePolicy finden Sie unter [Migrations- und Interoperabilitätsleitfaden für Organisationen, die Teams zusammen mit Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

**NOTIZEN**
 - Skype for Business IP-Telefone empfangen Anrufe, auch wenn sich der Benutzer im TeamsOnly-Modus befindet.  
 - Benutzer, die mit Telefonsystem- und Anrufplänen-Lizenzen für die Verwendung mit Skype for Business Online bereitgestellt wurden (z. B. wurde ihnen der Wert "OnlineVoiceRoutingPolicy" zugewiesen), haben die Registerkarte "Anrufe" in Teams aktiviert und können ausgehende PSTN-Anrufe von Teams tätigen, ohne dass Administratoren administrative Maßnahmen ergreifen müssen.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Konfigurieren von Benutzern für den Empfang aller eingehenden VOIP- und PSTN-Anrufe in Teams
Um sicherzustellen, dass Benutzer alle eingehenden VOIP- und PSTN-Anrufe in Teams erhalten, legen Sie den Koexistenzmodus des Benutzers im Microsoft Teams Admin Center auf "TeamsOnly" fest, oder verwenden Sie Skype for Business Remote-Windows PowerShell-Sitzung, um TeamsUpgradePolicy wie folgt zu aktualisieren:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Siehe auch
[Einrichten von Anrufplänen](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)

[Microsoft 365-Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)

[Skype for Business PowerShell-Cmdlet-Referenz](/powershell/module/skype)
