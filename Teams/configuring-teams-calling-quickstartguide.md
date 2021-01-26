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
description: Schnellstarthandbuch zum Konfigurieren von Anrufplänen in Microsoft Teams, damit Sie eine Gruppe von Benutzern einrichten und starten können.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799765"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams
==============================================================

Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.

Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).

> [!NOTE]
> Wir empfehlen, dass Sie parallel zu diesem Schnellstarthandbuch ["Telefonsystem](calling-plan-landing-page.md) mit Anrufplänen und [FastTrack"](https://aka.ms/cloudvoice) lesen, um einen erfolgreichen Rollout zu planen und vordrangen.

Durch das Hinzufügen von Anrufplänen – einer von Skype for Business unterstützten Microsoft 365- und Office 365-Funktion – können Sie jetzt Teams verwenden, um Telefonanrufe über das Telefonnetz (Public Switched Telephone Network, PSTN) über Festnetztelefone zu oder von Festnetz- und Mobiltelefonen zu führen und zu empfangen.

![Screenshot der Seite "Kontakte" in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams
Um die Registerkarte **"Anrufe"** in Teams zu aktivieren, müssen Benutzer in Teams 1:1-Anrufe aktivieren und einen Teams-Client verwenden, der 1:1-Anrufe in Teams unterstützt. Informationen zum Verwalten von 1:1-Anrufen in Teams finden Sie unter [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Um zu erfahren, welche Clients Anrufe unterstützen, lesen Sie die Grenzwerte und [Spezifikationen für Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)

> [!NOTE]
> Voicemail ist derzeit nicht auf der Registerkarte "Anrufe" verfügbar, es sei denn, der Benutzer ist für Anrufe über das Festnetz aktiviert. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Voraussetzungen für die Aktivierung der **Wählta pad** in Teams
Um die Registerkarte **"Wähltastpad"** in Teams zu aktivieren und Ihren Benutzern das Erstellen und Empfangen von Anrufen über das Festnetz zu ermöglichen, müssen Sie Benutzer für Telefonsystem und Anrufpläne bereitstellen. Informationen zum Einrichten von Anrufplänen finden Sie unter ["Einrichten von Anrufplänen".](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)
Darüber hinaus müssen Sie nur für Teams-Benutzer sicherstellen, dass "Private Anrufe zulassen" in der Anrufrichtlinie für Teams aktiviert ist. Weitere [Informationen finden Sie unter "Teams verwalten" während des Übergangs](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) zum neuen Microsoft Teams Admin Center.
> [!NOTE]
> Sie können auch das direkte Routing verwenden, um Ihren Benutzern das Anrufen und Empfangen von Anrufen über das Festnetz zu ermöglichen. Informationen zum Einrichten von Direct Routing finden Sie unter ["Konfigurieren des direkten Routings".](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Verwenden von TeamsUpgradePolicy zum Steuern, wo Anrufe landen
Um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype for Business eingehen, verwenden Administratoren TeamsUpgradePolicy, entweder über das [Microsoft Teams](https://aka.ms/teamsadmincenter) Admin Center oder über eine Remote-Windows PowerShell-Sitzung mit den Skype for Business-Cmdlets. [](https://docs.microsoft.com/powershell/module/skype)


Die Standardkonfiguration von TeamsUpgradePolicy ist der Islands-Modus, mit dem sichergestellt wird, dass vorhandene Geschäftsworkflows während einer Bereitstellung von Teams nicht unterbrochen werden. Standardmäßig werden VoIP-, PSTN- und Verbundanrufe an Ihre Benutzer weiterhin an Skype for Business geroutet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe an Teams zu aktivieren.  Wenn sich die Empfänger im Inselmodus befinden:

 - Eingehende VOIP-Anrufe, die aus Skype for Business stammen, werden immer im Skype for Business-Client des Empfängers landen.
 - Eingehende VOIP-Anrufe, die aus Teams stammen, werden in Teams landen, wenn sich der Absender und Empfänger *im selben Mandanten befinden.*
 - Eingehende VoIP-Partner-VOIP (unabhängig davon, welcher Client stammt) und ANRUFE über das Festnetz landen immer im Skype for Business-Client des Empfängers.
 
Um sicherzustellen, dass eingehende VOIP- und PSTN-Anrufe immer im Teamclient eines Benutzers landen, aktualisieren Sie den Koexistenzmodus des Benutzers auf "TeamsOnly" (d. h., weisen Sie ihm die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zu.  Weitere Informationen zu Koexistenzmodi und TeamsUpgradePolicy finden Sie unter Migrations- und Interoperabilitätsanleitungen für Organisationen, die Teams zusammen mit [Skype for Business verwenden.](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**HINWEISE**
 - Skype for Business-IP-Telefone empfangen Anrufe, auch wenn sich der Benutzer im TeamsOnly-Modus befindet.  
 - Benutzer, die über Telefonsystem- und Anrufplanlizenzen für die Verwendung mit Skype for Business Online bereitgestellt wurden (z. B. ihnen wurde der Wert "OnlineVoiceRoutingPolicy" zugewiesen), haben die Registerkarte "Anrufe" in Teams aktiviert und können ausgehende Anrufe über das Festnetz von Teams aus führen, ohne dass ein Administrator Administratoraktion ergreifen muss.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Konfigurieren von Benutzern für den Empfang aller eingehenden VOIP- und FESTNETZanrufe in Teams
Um sicherzustellen, dass Benutzer alle eingehenden VOIP- und PSTN-Anrufe in Teams erhalten, legen Sie den Koexistenzmodus des Benutzers im Microsoft Teams Admin Center auf TeamsOnly fest, oder verwenden Sie die Skype for Business-Remote-Windows PowerShell-Sitzung, um TeamsUpgradePolicy wie folgt zu aktualisieren:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Siehe auch
[Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Microsoft 365-Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)

[Skype for Business PowerShell-Cmdlet - Referenz](https://docs.microsoft.com/powershell/module/skype)

