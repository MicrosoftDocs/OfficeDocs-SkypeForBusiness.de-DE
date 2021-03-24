---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Schnellstarthandbuch zum Konfigurieren von Anrufplänen in Microsoft Teams, damit Sie eine Gruppe von Benutzern einrichten und ausführen können.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101181"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams
==============================================================

Dieser Leitfaden hilft Ihnen, eine Gruppe von Benutzern zu unterstützen, damit sie Anrufpläne in Teams erkunden können.

Lesen Sie die Ankündigung von Anrufplänen vom 12. Dezember 2017 in Teams: Intelligente Kommunikation nimmt den nächsten Schritt mit Anrufen [in Teams vor.](https://aka.ms/ipyqus)

> [!NOTE]
> Wir empfehlen, parallel zu diesem Schnellstartleitfaden [Telefonsystem](calling-plan-landing-page.md) mit Anrufplänen und [FastTrack](https://aka.ms/cloudvoice) zu lesen, um einen erfolgreichen Rollout zu planen und vor sich zu führen.

Indem Sie Anrufpläne hinzufügen – ein Microsoft 365- und Office 365-Feature, das von Skype for Business unterstützt wird – können Sie jetzt Teams verwenden, um Anrufe von oder zu Festnetztelefonen und Mobiltelefonen über das öffentliche Telefonnetz (PSTN) zu führen und zu empfangen.

![Screenshot der Seite "Kontakte" in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Teams
Um die Registerkarte **Anrufe** in Teams zu aktivieren, müssen benutzer in Teams 1:1-Anrufe aktiviert haben und einen Teams-Client verwenden, der 1:1-Anrufe von Teams unterstützt. Informationen zum Verwalten von 1:1-Anrufen in Teams finden Sie unter [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Informationen zu den Clients, die Anrufe unterstützen, finden Sie unter [Grenzwerte und Spezifikationen für Microsoft Teams.](./limits-specifications-teams.md)

> [!NOTE]
> Derzeit steht Voicemail nicht auf der Registerkarte Anrufe zur Verfügung, es sei denn, der Benutzer ist für PSTN-Anrufe aktiviert. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Voraussetzungen für das Aktivieren der **Wählta0** in Teams
Um die Registerkarte **Wähltastblock** in Teams zu aktivieren und Ihren Benutzern das Anrufen und Empfangen von FESTNETZanrufen zu ermöglichen, müssen Sie Benutzer für Telefonsystem- und Anrufpläne bereitstellen. Informationen zum Einrichten von Anrufplänen finden Sie unter [Einrichten von Anrufplänen.](./set-up-calling-plans.md)
Darüber hinaus müssen Sie nur für Teams-Benutzer sicherstellen, dass "Private Anrufe zulassen" in der Anrufrichtlinie von Teams aktiviert ist. Weitere Informationen finden Sie unter Verwalten von Teams während des Übergangs zum neuen [Microsoft Teams Admin Center.](./manage-teams-skypeforbusiness-admin-center.md)
> [!NOTE]
> Sie können auch Direct Routing verwenden, um Benutzern das Erstellen und Empfangen von PSTN-Anrufen zu ermöglichen. Informationen zum Einrichten von Direct Routing finden Sie unter [Konfigurieren von Direct Routing](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Verwenden von TeamsUpgradePolicy zum Steuern, wo Anrufe landen
Um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype for Business landen, verwenden Administratoren TeamsUpgradePolicy, entweder über das [Microsoft Teams Admin Center](https://aka.ms/teamsadmincenter) oder über eine Remote-Windows PowerShell-Sitzung mit den Skype for Business-Cmdlets. [](/powershell/module/skype)


Die Standardkonfiguration von TeamsUpgradePolicy ist der Inselmodus, der sicherstellen soll, dass vorhandene Geschäftsworkflows während einer Teams-Bereitstellung nicht unterbrochen werden. Standardmäßig werden VoIP-, PSTN- und Verbundanrufe an Ihre Benutzer weiterhin an Skype for Business geroutet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe an Teams zu aktivieren.  Wenn empfänger im Inselmodus sind:

 - Eingehende VOIP-Anrufe, die aus Skype for Business stammen, landen immer im Skype for Business-Client des Empfängers.
 - Eingehende VOIP-Anrufe, die aus Teams stammen, landen in Teams, wenn sich Absender und Empfänger *im gleichen Mandanten befinden.*
 - Eingehende VoIP-Verbundanrufe (unabhängig davon, welcher Client stammt) und PSTN-Anrufe landen immer im Skype for Business-Client des Empfängers.
 
Um sicherzustellen, dass eingehende VOIP- und PSTN-Anrufe immer im Teams-Client eines Benutzers landen, aktualisieren Sie den Koexistenzmodus des Benutzers auf TeamsOnly (d. h., weisen Sie ihm die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zu.  Weitere Informationen zu Koexistenzmodi und TeamsUpgradePolicy finden Sie unter Migrations- und Interoperabilitätsleitfäden für Organisationen, die Teams zusammen mit [Skype for Business verwenden.](./migration-interop-guidance-for-teams-with-skype.md)

**NOTIZEN**
 - Skype for Business -IP-Telefone empfangen Anrufe, auch wenn sich der Benutzer im TeamsOnly-Modus befindet.  
 - Benutzer, die mit Lizenzen für Telefonsystem und Anrufpläne für die Verwendung mit Skype for Business Online bereitgestellt wurden (z. B. wurde ihnen der Wert OnlineVoiceRoutingPolicy zugewiesen), haben die Registerkarte Anrufe in Teams aktiviert und können ausgehende PSTN-Anrufe von Teams platzieren, ohne dass Administratoren administrative Maßnahmen ergreifen müssen.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>So konfigurieren Sie Benutzer für den Empfang aller eingehenden VOIP- und PSTN-Anrufe in Teams
Um sicherzustellen, dass Benutzer alle eingehenden VOIP- und PSTN-Anrufe in Teams empfangen, legen Sie den Koexistenzmodus des Benutzers auf TeamsOnly im Microsoft Teams Admin Center fest, oder verwenden Sie die Skype for Business Remote Windows PowerShell-Sitzung, um TeamsUpgradePolicy wie folgt zu aktualisieren:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Mehr dazu
[Einrichten von Anrufplänen](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)

[Microsoft 365-Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)

[Skype for Business PowerShell-Cmdletreferenz](/powershell/module/skype)