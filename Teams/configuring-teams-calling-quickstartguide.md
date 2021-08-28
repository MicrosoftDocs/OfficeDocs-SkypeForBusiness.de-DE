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
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab563bb4acd4ea79c35b90dc691bd95f506e5acd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593149"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams

Dieser Leitfaden soll Ihnen helfen, eine Reihe von Benutzern ein- und aus der Reihe zu machen, damit sie Anrufpläne in ihrer Teams.

Lesen Sie die Ankündigung von Anrufplänen in Teams: [Intelligent Communications](https://aka.ms/ipyqus) vom 12. Dezember 2017, die den nächsten Schritt mit Anrufen in Teams

> [!NOTE]
> Wir empfehlen, dass Sie parallel zu diesem [](calling-plan-landing-page.md) Schnellstarthandbuch Informationen Telefonsystem [](https://aka.ms/cloudvoice) Anrufpläne und FastTrack, um einen erfolgreichen Rollout zu planen und vorlesen zu lassen.

Durch das Hinzufügen von Anrufplänen – einem von Skype for Business unterstützten Microsoft 365- und Office 365-Feature – können Sie jetzt Teams verwenden, um Telefonanrufe über das Telefonnetz (Public Switched Telephone Network, PSTN) an Festnetztelefone und Mobiltelefone zu oder von diesen zu empfangen.

![Screenshot der Seite "Kontakte" in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Voraussetzungen für das Aktivieren der **Registerkarte** "Anrufe" in Teams
Zum Aktivieren  der Registerkarte Anrufe in Teams müssen Benutzer in Teams 1:1-Anrufe aktivieren und einen Teams-Client verwenden, der 1:1-Anrufe Teams unterstützt. Informationen zum Verwalten von 1:1-Anrufen in Teams finden Sie unter [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy) Um zu erfahren, welche Clients Anrufe unterstützen, lesen Sie [Limits und Spezifikationen für Microsoft Teams.](./limits-specifications-teams.md)

> [!NOTE]
> Voicemail steht derzeit nicht auf der Registerkarte Anrufe zur Verfügung, es sei denn, der Benutzer ist für PSTN-Anrufe aktiviert. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Voraussetzungen für die Aktivierung der **Wählta nicht** Teams
Um die Registerkarte **Wähltast in** Teams zu aktivieren und Ihren Benutzern das Anrufen und Empfangen von PSTN-Anrufen zu ermöglichen, müssen Sie Benutzer für Telefonsystem und Anrufpläne bereitstellen. Informationen zum Einrichten von Anrufplänen finden Sie unter [Einrichten von Anrufplänen.](./set-up-calling-plans.md)
Darüber hinaus müssen Sie Teams Benutzer in der Richtlinie für Private Anrufe zulassen sicherstellen, dass Teams aktiviert ist. Weitere [Informationen Teams](./manage-teams-skypeforbusiness-admin-center.md) Sie unter Verwalten von E-Microsoft Teams während des Übergangs zum neuen Admin Center.
> [!NOTE]
> Sie können auch Direct Routing verwenden, um Ihren Benutzern das Anrufen und Empfangen von PSTN-Anrufen zu ermöglichen. Informationen zum Einrichten von Direct-Routing finden Sie unter [Konfigurieren von Direct-Routing.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Verwenden von TeamsUpgradePolicy zum Steuern, wo Anrufe landen
Um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype for Business landen, verwenden Administratoren TeamsUpgradePolicy, entweder [über das Microsoft Teams Admin](https://aka.ms/teamsadmincenter) Center oder über eine Remote-Windows PowerShell-Sitzung mit den Skype for Business-Cmdlets. [](/powershell/module/skype)


Die Standardkonfiguration von TeamsUpgradePolicy ist der Islands-Modus, mit dem sichergestellt wird, dass vorhandene geschäftliche Workflows während einer Teams unterbrochen werden. Standardmäßig werden VoIP-, PSTN- und Partneranrufe an Ihre Benutzer weiterhin an Skype for Business geroutet, bis Sie die Richtlinie aktualisiert haben, um eingehende Anrufe an Ihre Teams.  Wenn sich die Empfänger im Islands-Modus befinden:

 - Eingehende VOIP-Anrufe, die aus Skype for Business stammen, landen immer im Skype for Business des Empfängers.
 - Eingehende VOIP-Anrufe, die aus einem Teams stammen, landen in Teams, wenn sich der Absender und Empfänger *im selben Mandanten befinden.*
 - Eingehende VoIP-Partneranrufe (unabhängig vom Ursprung des Clients) und PSTN-Anrufe landen immer im Skype for Business des Empfängers.
 
Um sicherzustellen, dass eingehende VOIP- und PSTN-Anrufe immer im Teams-Client eines Benutzers landen, aktualisieren Sie den Koexistenzmodus des Benutzers auf TeamsOnly (d. h., weisen Sie ihm die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.  Weitere Informationen zu Koexistenzmodi und TeamsUpgradePolicy finden Sie unter Richtlinien für Migration und Interoperabilität für Organisationen, [die](./migration-interop-guidance-for-teams-with-skype.md) Teams mit Skype for Business

**HINWEISE**
 - Skype for Business IP-Telefone empfangen Anrufe, auch wenn sich der Benutzer im TeamsOnly-Modus befindet.  
 - Benutzer, die über Telefonsystem- und Anrufplanlizenzen für die Verwendung mit Skype for Business Online bereitgestellt wurden (z. B. ihnen wurde der Wert OnlineVoiceRoutingPolicy zugewiesen), haben die Registerkarte Anrufe in Teams aktiviert und können ausgehende PSTN-Anrufe von Teams abnetzen, ohne dass die Administratoren Verwaltungsaufgaben ergreifen müssen.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Konfigurieren von Benutzern für den Empfang aller eingehenden VOIP- und PSTN-Anrufe Teams
Um sicherzustellen, dass Benutzer alle eingehenden VOIP- und PSTN-Anrufe in Teams erhalten, legen Sie den Koexistenzmodus des Benutzers im Microsoft Teams Admin Center auf TeamsOnly fest, oder verwenden Sie die Skype for Business-Remote-Windows PowerShell-Sitzung, um TeamsUpgradePolicy wie folgt zu aktualisieren:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Mehr dazu
[Einrichten von Anrufplänen](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)

[Microsoft 365-Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)

[Skype for Business PowerShell-Cmdlet-Referenz](/powershell/module/skype)
