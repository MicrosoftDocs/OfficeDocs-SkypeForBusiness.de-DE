---
title: "Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e38317132190b3035f37509d1fa7b2da5e4785c7
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2017
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
Um die Registerkarte **Anrufe** in Microsoft Teams zu aktivieren und Ihren Benutzern das Tätigen und Empfangen von PSTN-Anrufen zu ermöglichen, müssen Sie Benutzer für das Telefonsystem und Anrufpläne bereitstellen. Eine entsprechende Anleitung finden Sie unter [Einrichten von Anrufplänen](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).

> [!IMPORTANT]
> Beachten Sie beim Konfigurieren von Anrufplänen in Microsoft Teams die folgenden Einschränkungen:
> * **Hybridtelefonie wird in Microsoft Teams nicht unterstützt.** – Hybridtelefonie wird zurzeit in Microsoft Teams nicht unterstützt. Kunden, die Hybridtelefonie nutzen, sollten die Richtlinien für den Empfang von Anrufen in Microsoft Teams nicht ändern, da dies zu Dienstunterbrechungen führt.
> * **Partneranrufe werden in Microsoft Teams nicht unterstützt.** – Partneranrufe (Anrufe zwischen Mandanten/Firmen) werden zurzeit in Microsoft Teams nicht unterstützt. Solange die Unterstützung in Microsoft Teams nicht vorhanden ist, werden Partneranrufe immer an Skype for Business weitergeleitet. Dabei spielt es keine Rolle, wie Sie die Anruffunktion konfigurieren.

## <a name="teams-interop-policy-configuration"></a>Konfiguration der Interop-Richtlinie für Microsoft Teams
Um in Microsoft Teams Anrufe empfangen zu können, müssen Sie die Interop-Richtlinie für Microsoft Teams aktualisieren. Verwenden Sie dazu eine Windows PowerShell-Sitzung und die [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)-Cmdlets für Skype for Business, um Anrufe an Microsoft Teams umzuleiten. Weitere Informationen zur Interop-Richtlinie für Microsoft Teams finden Sie unter [Interoperabilität von Microsoft Teams und Skype for Business](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).

> [!TIP]
> Die benötigten PowerShell-Cmdlets finden Sie, indem Sie „CsTeamsInteropPolicy“ in das Feld **Filter** in der [Dokumentation zu den PowerShell-Cmdlets für Skype for Business](https://docs.microsoft.com/powershell/module/skype) eingeben.

### <a name="default-teams-interop-policy"></a>Interop-Standardrichtlinie für Microsoft Teams
Microsoft Teams enthält eine Standardrichtlinienkonfiguration, die sicherstellen soll, dass vorhandene Geschäftsworkflows bei der Bereitstellung von Microsoft Teams nicht gestört werden. VoIP-, PSTN- und Partneranrufe an Ihre Benutzer werden standardmäßig weiterhin an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe in Microsoft Teams zu aktivieren. Dadurch werden unbeabsichtigte Unterbrechungen der VoIP-Dienste vermieden, wenn Sie mit dem Pilotprojekt und der Bereitstellung von Microsoft Teams beginnen.

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

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>Konfigurieren von Microsoft Teams für die Verwendung der Standardrichtlinie
Die globale Interop-Richtlinie für Microsoft Teams wird standardmäßig auf alle Benutzer in Ihrem Mandanten angewendet. Sie ist mit den oben beschriebenen Standardeinstellungen konfiguriert. Wenn Sie aus einem bestimmten Grund Ihren Benutzern andere Richtlinien zugewiesen haben und die Standardeinstellung wiederherstellen möchten, müssen Sie die globale Interop-Richtlinie für Microsoft Teams über eine Windows PowerShell-Remotesitzung mit Skype for Business anwenden:

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> Es ist zwar möglich, die globale Interop-Richtlinie für Microsoft Teams zu ändern, sodass nicht die Standardwerte verwendet werden, aber wir raten dringend davon ab. 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Konfigurieren von Microsoft Teams für den Empfang von eingehenden PSTN-Anrufen
Um eingehende PSTN-Anrufe in Microsoft Teams zu empfangen, müssen Sie Microsoft Teams als Standardanwendung für Anrufe konfigurieren. Dazu wenden Sie die Interop-Richtlinie für Microsoft Teams an und legen dabei den Parameter `CallingDefaultClient` auf „Teams“ (Microsoft Teams) fest.

> [!IMPORTANT]
> Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden. Dann können sich diese Benutzer mit den nützlichen neuen Anruffunktionen in Microsoft Teams vertraut machen, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.

Mit der folgenden vorkonfigurierten Interop-Richtlinie für Microsoft Teams können Sie eingehende PSTN-Anrufe an Microsoft Teams weiterleiten:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

Die oben gezeigte Richtlinie legt die folgenden Verhaltensweisen fest:
* **Für bestehende Skype for Business-Kunden** leitet diese Richtlinie eingehende Anrufe an Microsoft Teams um. Dies gilt sowohl für VoIP-Anrufe (aus Microsoft Teams und Skype for Business) als auch für PSTN-Anrufe. Partneranrufe werden weiterhin in Skype for Business empfangen. 
* **Kunden ohne Skype for Business** empfangen, wenn die Richtlinie wirksam ist, PSTN-Anrufe in Microsoft Teams. Partneranrufe werden zurzeit in Microsoft Teams **nicht unterstützt**.

> [!WARNING]
> Zurzeit wirkt sich das Ändern von `CallingDefaultClient` in Microsoft Teams auch auf Anrufe an Skype for Business-IP-Telefone aus. Eingehende Anrufe werden nicht an den Telefonen empfangen und klingeln nur bei Microsoft Teams-Clients. Weitere Informationen zu vorhandenen zertifizierten SIP-Telefonen finden Sie unter [Von Skype for Business zu Microsoft Teams: Roadmap der Funktionen](https://aka.ms/skype2teamsroadmap).

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>Konfigurieren von Microsoft Teams für den Empfang von PSTN-Anrufen
Wenden Sie die Interop-Richtlinie für Microsoft Teams wie oben beschrieben über eine Windows PowerShell-Remotesitzung mit Skype for Business an, um Anrufe an Microsoft Teams umzuleiten:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>Konfigurieren von Microsoft Teams, um Benutzern das Ändern ihrer bevorzugten Anrufanwendung zu ermöglichen
Wenn Sie es den Benutzern ermöglichen möchten, selbst über ihre bevorzugte Anrufanwendung zu entscheiden (Empfang von Anrufen in Microsoft Teams oder in Skype for Business), müssen Sie eine benutzerdefinierte Interop-Richtlinie für Microsoft Teams erstellen, die den Parameter `AllowEndUserClientOverride` aktiviert.

Das folgende Beispiel zeigt, wie Sie in der Interop-Richtlinie für Microsoft Teams die Auswahl der bevorzugten Anrufanwendung durch die Benutzer aktivieren:

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Wenn Sie diese Richtlinie auf die Benutzer angewendet haben, ist im Microsoft Teams-Client die Option zum Ändern der bevorzugten Anrufanwendung verfügbar, und die Benutzer können die Änderungen selbst vornehmen.

![Option „Bevorzugte Anrufanwendung“](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>Erstellen und Anwenden der benutzerdefinierten Interop-Richtlinie für Microsoft Teams
Um die benutzerdefinierte Interop-Richtlinie für Microsoft Teams wie oben beschrieben über eine Windows PowerShell-Remotesitzung mit Skype for Business zu erstellen, führen Sie Folgendes aus:

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>Siehe auch
[Einrichten von Anrufplänen](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Interoperabilität von Microsoft Teams und Skype for Business](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[PowerShell-Cmdlet-Referenz für Skype for Business](https://docs.microsoft.com/powershell/module/skype)

[PowerShell-Cmdlet-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
