---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e043633749e0ef2dba41b5b3b18776cfbe1c497
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236573"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams
==============================================================

Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.

Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).

> [!NOTE]
> Wir empfehlen, dass Sie parallel zu diesem Schnellstarthandbuch das [Telefon System mit Anrufplänen](calling-plan-landing-page.md) und Kurzübersicht lesen [](https://aka.ms/cloudvoice) , um einen erfolgreichen Rollout zu planen und voranzutreiben.

Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.

![Screenshot mit der Seite "Kontakte" in Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams
Um die Registerkarte " **Anrufe** " in Teams zu aktivieren, müssen die Benutzer 1:1-Anrufe in Teams aktiviert haben und einen Teams-Client verwenden, der 1:1 Teams unterstützt. Informationen zum Verwalten von 1:1-anrufen in Teams finden Sie unter [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Wenn Sie wissen möchten, welche Kundenanrufe unterstützen, lesen Sie die [Grenzwerte und Spezifikationen für Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Voicemail steht zurzeit nicht auf der Registerkarte Anrufe zur Verfügung, es sei denn, der Benutzer ist für PSTN-Anrufe aktiviert. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Voraussetzungen für die Aktivierung der **Wähltastatur** in Teams
Um die Registerkarte **Wähltastatur** in Teams zu aktivieren und ihren Benutzern die Möglichkeit zu bieten, PSTN-Anrufe zu tätigen und zu empfangen, müssen Sie die Benutzer für Telefon System-und Anrufpläne bereitstellen. Informationen zum Einrichten von Anrufplänen finden Sie unter [Einrichten von Anrufplänen](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Sie können auch die direkte Weiterleitung verwenden, um es Ihren Benutzern zu ermöglichen, PSTN-Anrufe zu tätigen und zu empfangen. Informationen zum Einrichten des direkten Routings finden Sie unter [Konfigurieren des direkten Routings](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Verwenden von TeamsUpgradePolicy, um zu steuern, wo Anrufe landen
Um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype for Business landen, verwenden Administratoren TeamsUpgradePolicy entweder mithilfe von [Microsoft Teams Admin Center](https://aka.ms/teamsadmincenter) oder mithilfe einer Remote-Windows PowerShell-Sitzung mit dem [Skype for Business](https://docs.microsoft.com/powershell/module/skype) Cmdlets.


Die Standardkonfiguration von TeamsUpgradePolicy ist der Inseln-Modus, mit dem sichergestellt werden soll, dass vorhandene Geschäftsworkflows während einer Team Bereitstellung nicht unterbrochen werden. Standardmäßig werden VoIP-, PSTN-und Verbund Anrufe an Ihre Benutzer weiter an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe an Teams zu ermöglichen.  Wenn sich die Empfänger im Inseln-Modus befinden:

 - Eingehende VoIP-Anrufe, die von Skype for Business stammen, landen immer im Skype for Business-Client des Empfängers.
 - Eingehende VoIP-Anrufe, die in Teams entstanden sind, landen in Teams, *Wenn sich Absender und Empfänger im gleichen Mandanten befinden*.
 - Eingehendes Federated-VoIP (unabhängig davon, welcher Client stammt) und PSTN-Anrufe landen immer im Skype for Business-Client des Empfängers.
 
Um sicherzustellen, dass eingehende VoIP-und PSTN-Anrufe immer im Team-Client eines Benutzers landen, aktualisieren Sie den Koexistenzmodus des Benutzers auf TeamsOnly (was bedeutet, weisen Sie ihm die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.  Weitere Informationen zu den Modi für Koexistenz und TeamsUpgradePolicy finden Sie unter [Leitfaden zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**Notizen**
 - Skype for Business-IP-Telefone empfangen Anrufe, auch wenn sich der Benutzer im TeamsOnly-Modus befindet.  
 - Benutzer, die über Telefon System-und Anruf Plan Lizenzen für die Nutzung mit Skype for Business Online bereitgestellt wurden (beispielsweise einem Wert von OnlineVoiceRoutingPolicy), haben die Registerkarte "Anrufe" in Teams aktiviert und können ausgehende PSTN-Anrufe von Teams ohne Administratoren müssen administrative Schritte Unternehmen.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Konfigurieren von Benutzern für den Empfang aller eingehenden VoIP-und PSTN-Anrufe in Teams
Wenn Sie sicherstellen möchten, dass Benutzer alle eingehenden VoIP-und PSTN-Anrufe in Teams empfangen, legen Sie den Koexistenzmodus des Benutzers im Microsoft Teams Admin Center auf TeamsOnly fest, oder verwenden Sie die Skype for Business-Remote-Windows PowerShell-Sitzung, um TeamsUpgradePolicy wie folgt zu aktualisieren:

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Siehe auch
[Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Telefon System mit Anrufplänen](calling-plan-landing-page.md)

[Skype for Business PowerShell-Cmdlet-Referenz](https://docs.microsoft.com/powershell/module/skype)

