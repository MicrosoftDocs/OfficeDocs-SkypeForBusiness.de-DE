---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams
author: arachmanGitHub
ms.author: Rowille
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: Rowille, lolaj
search.appverid: MET150
description: Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6c719d17938986ff6568b73864bc131667e4e7
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401983"
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
Zum Aktivieren der Registerkarte **Anrufe** in Teams benötigen Benutzer 1:1 aktiviert werden, Teams aufrufen und Verwenden von Clientidentität Teams, die 1:1-Teams aufrufen unterstützt. Weitere Informationen zum Verwalten von 1:1 einwählen, Teams lesen Sie [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Um zu erfahren, welche Clients aufrufen unterstützen, lesen Sie [Grenzwerte und Spezifikationen für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Derzeit wird Voicemail in der Registerkarte Anrufe nicht verfügbar, wenn der Benutzer für PSTN-Anrufe aktiviert ist. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Voraussetzungen für das **Wähltastenfeld** im Teams aktivieren
Zum Aktivieren der Registerkarte **Wähltastatur** in Teams und ermöglichen die Benutzer das tätigen und annehmen von PSTN-Anrufe müssen Sie die Bereitstellung von Benutzern für Telefonsystem und plant aufrufen. Zum Aufrufen von plant einrichten finden Sie unter [Einrichten von plant aufrufen](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).

> [!NOTE]
> Direktes Routing können auch Ihre Benutzerberechtigungen zum tätigen und annehmen von PSTN-Anrufe. Weitere Informationen zum Einrichten der direkten Routing lesen Sie [Direkten Routing konfigurieren](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Verwenden von TeamsUpgradePolicy zum Steuerelement sorgt, in dem Anrufe
Administratoren verwenden um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype für Unternehmen sorgt TeamsUpgradePolicy, verwenden entweder [Microsoft-Teams-Verwaltungskonsole](https://aka.ms/teamsadmincenter) oder mithilfe einer Windows PowerShell-Remotesitzung mit der [Skype für Business](https://docs.microsoft.com/powershell/module/skype) Cmdlets.


Die Standardkonfiguration der TeamsUpgradePolicy ist Inseln-Modus, die entworfen wurde, um sicherzustellen, dass diese vorhandenen Business, Workflows nicht während der Bereitstellung Teams unterbrochen werden. Standardmäßig werden VoIP, PSTN und Verbundpartner Anrufe an Ihre Benutzer weiterhin an Skype für Unternehmen weitergeleitet werden, bis Sie die Richtlinie so aktivieren eingehenden Anrufe von Teams aktualisieren.  Wenn Empfänger im Modus Inseln sind:

 - Eingehende VOIP ruft diese originated in Skype für Unternehmen immer Flächen, die in der Aufgabenliste des Empfängers Skype für Business-Client.
 - Eingehende VOIP aufruft, die in Teams Land in Teams, *Wenn der Absender und Empfänger in derselben mandantenorganisation sind*stammt.
 - Eingehende federated VOIP (unabhängig von der Clientcomputer stammt) und PSTN-immer Anrufe Flächen, die in der Aufgabenliste des Empfängers Skype für Business-Client.
 
Um sicherzustellen, dass eingehende VoIP- und PSTN-Anrufe immer Land Teams-Client des Benutzers, Aktualisierungsmodus des Benutzers Koexistenz um TeamsOnly werden (d. h. diese Instanz "UpgradeToTeams" von TeamsUpgradePolicy zuordnen.  Weitere Informationen zu Koexistenz Modi und TeamsUpgradePolicy finden Sie unter [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**Notizen**
 - Skype für Business IP-Telefone erhält Anrufe, selbst wenn der Benutzer im TeamsOnly Modus befindet.  
 - Benutzer, die mit Telefonsystem und Pläne Aufrufen von Lizenzen für die Verwendung mit Skype für Business Online (z. B. haben sie einen Wert von OnlineVoiceRoutingPolicy zugewiesen wurde), wird die Registerkarte Anrufe in Teams aktiviert haben und ausgehende PSTN-Anrufe von bereitgestellt wurden Teams ohne Administratoren administrative Maßnahmen ergreifen müssen.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Zum Konfigurieren von Benutzern Empfang alle eingehenden VoIP- und PSTN-Anrufe in Teams
Um sicherzustellen, dass Benutzer in Teams alle eingehenden VoIP- und PSTN-Anrufe empfangen, legen Sie die Benutzermodus Koexistenz auf TeamsOnly in der Verwaltungskonsole von Microsoft-Teams, oder verwenden Sie Skype für Business remote Windows PowerShell-Sitzung TeamsUpgradePolicy wie folgt aktualisiert:

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>Siehe auch
[Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Telefonsystem mit dem Aufrufen der Pläne](calling-plan-landing-page.md)

[Skype für Referenz Business PowerShell-Cmdlets](https://docs.microsoft.com/powershell/module/skype)

