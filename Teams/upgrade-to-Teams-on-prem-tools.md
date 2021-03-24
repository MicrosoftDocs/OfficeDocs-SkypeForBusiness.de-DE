---
title: Tools für das Upgrade von einer lokalen Skype for Business-Bereitstellung auf Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Tools für ein Upgrade von Skype for Business auf Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5585a2d2995b2f7d470c4d07eab3f5bb7f1934c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097501"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Tools für das Upgrade auf Teams &mdash; für IT-Administratoren

In diesem Artikel werden Tools für das Upgrade von Skype for Business auf Teams beschrieben. 

Bevor Sie mit dem Upgrade beginnen, empfiehlt Microsoft die folgenden Artikel, in denen wichtige Upgradekonzepte und Verhalten der Koexistenz beschrieben werden:

- [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Tools zum Verwalten des Upgrades

Unabhängig von der von Ihnen verwendeten Upgrademethode verwalten Sie für Benutzer, die bereits Über Skype for Business Online verfügen, den Übergang zu TeamsOnly mithilfe von [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), das den Koexistenzmodus eines Benutzers steuert. Für Benutzer mit einem lokalen Konto in Skype for Business Server verwenden Sie sie auch, um sie in `Move-CsUser` [die Cloud zu verschieben.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Weitere Informationen zu den einzelnen Modi finden Sie unter [Koexistenzmodi](migration-interop-guidance-for-teams-with-skype.md).

> [!NOTE]
> Wenn Sie derzeit Skype for Business Online Connector zum Verwalten Ihrer Dienste verwenden, müssen Sie zum Teams PowerShell-Modul wechseln und Ihre vorhandenen PowerShell-Skripts aktualisieren. Weitere Informationen finden Sie unter Wechseln von [Skype for Business Online Connector zum Teams PowerShell-Modul.](teams-powershell-move-from-sfbo.md)

Ganz gleich, ob Sie einen Übergang zu Auswahlfunktionen mithilfe von Skype for Business-Modi durchführen oder einfach über die Standardkonfiguration Islands auf den TeamsOnly-Modus aktualisieren, TeamsUpgradePolicy ist das primäre Tool für Benutzer, die bereits über Skype for Business Online verfügen. Wie jede andere Richtlinie in Teams können Sie TeamsUpgradePolicy direkt einem Benutzer zuweisen. Sie können die Richtlinie auch als mandantenweite Standardeinstellung festlegen. Jede Zuordnung zu einem Benutzer hat Vorrang vor der Standardeinstellung des Mandanten.  Sie können die Richtlinie in der Teams Admin Console und in PowerShell verwalten.

Sie können auch jedem Modus von TeamsUpgradePolicy , mit Ausnahme des TeamsOnly-Modus, Benutzer zuweisen, die in Skype for Business lokal heimisch sind. **Der TeamsOnly-Modus kann nur** einem Benutzer zugewiesen werden, der bereits in Skype for Business Online zu Hause ist. Dies liegt daran, dass in Verbindung mit Skype for Business-Benutzern und verbund- und Microsoft 365 Phone System-Funktionen nur möglich ist, wenn der Benutzer in Skype for Business Online zu Hause ist. Darüber hinaus können Sie den **TeamsOnly-Modus** nicht als mandantenweite Standardeinstellung zuweisen, wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen (die durch das Vorhandensein eines lyncdiscover-DNS-Eintrags erkannt wird, der auf einen anderen Speicherort als Office 365 verweist.

Benutzer mit lokalen Skype for Business-Konten müssen mithilfe von Move-CsUser im lokalen Toolset von Skype for Business online [(entweder](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) zu Skype for Business Online oder direkt zu Teams) verschoben werden. Diese Benutzer können in 1 oder 2 Schritten nach TeamsOnly verschoben werden:

-   1 Schritt: Geben Sie den Schalter -MoveToTeams in Move-CsUser an. Dazu ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 oder höher erforderlich.

-   2 Schritte: Gewähren Sie nach dem Ausführen von Move-CsUser den TeamsOnly-Modus für den Benutzer, der TeamsUpgradePolicy verwendet.

Im Gegensatz zu anderen Richtlinien ist es nicht möglich, neue Instanzen von TeamsUpgradePolicy in Microsoft 365 oder Office 365 zu erstellen. Alle vorhandenen Instanzen sind in den Dienst integriert.  (Beachten Sie, dass der Modus eine Eigenschaft in TeamsUpgradePolicy und nicht der Name einer Richtlinieninstanz ist.) In einigen - aber nicht allen - Fällen ist der Name der Richtlinieninstanz mit dem Modus identisch. Insbesondere zum Zuweisen des TeamsOnly-Modus zu einem Benutzer gewähren Sie diesem Benutzer die Instanz "UpgradeToTeams" von TeamsUpgradePolicy. Wenn Sie eine Liste aller Instanzen sehen möchten, können Sie den folgenden Befehl ausführen:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Um einen Onlinebenutzer in den TeamsOnly-Modus zu aktualisieren, weisen Sie die Instanz "UpgradeToTeams" zu: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Wenn Sie einen lokalen Skype for Business-Benutzer auf den TeamsOnly-Modus aktualisieren möchten, verwenden Move-CsUser im lokalen Toolset:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Führen Sie den folgenden Befehl aus, um den Modus für alle Benutzer im Mandanten zu ändern, mit Ausnahme der Benutzer, die über eine explizite Pro-Benutzer-Berechtigung verfügen (die Rangfolge hat):

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Wenn Sie über benutzer mit lokalen Skype for Business-Konten verfügen, können Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen. Sie müssen diese Benutzer mithilfe von Move-CsUser einzeln in die Cloud verschieben.


## <a name="using-notifications-in-skype-for-business-clients"></a>Verwenden von Benachrichtigungen in Skype for Business-Clients

Administratoren können endbenutzerbenachrichtigungen im Skype for Business-Client bereitstellen, um die Benutzer darüber zu informieren, dass sie bald auf Teams aktualisiert werden, wie in der folgenden Abbildung dargestellt. Eine Woche vor dem Geplanten Upgrade einer Benutzergruppe auf den TeamsOnly-Modus möchte der Administrator diese Benachrichtigungen beispielsweise für diese Benutzergruppe aktivieren. Diese Benachrichtigungen werden mithilfe einer Instanz von TeamsUpgradePolicy mit NotifySfbUsers=true aktiviert.  Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entspricht.  Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entspricht. 

![Diagramm mit Benachrichtigungen](media/teams-upgrade-sfb-with-notifications.png)

Wenn Ihre Benutzer in Skype for Business Online zu Hause sind, weisen Sie einfach die Richtlinieninstanz zu, die denselben Modus wie der Benutzer hat, aber mit NotifySfbUsers=true. 

Wenn Ihre Benutzer lokal in Skype for Business Server zu Hause sind, müssen Sie das lokale Toolset verwenden, und Sie benötigen Skype for Business Server 2019 oder CU8 für Skype for Business Server 2015. Für Benutzer, die in Skype for Business Server lokal heimische Benutzer sind, wird die Moduseigenschaft aus der Onlineinstanz von TeamsUpgradePolicy berücksichtigt, die NotifySfbUsers-Eigenschaft jedoch nicht. Wenn Benachrichtigungen erwünscht sind, müssen Sie eine lokale Instanz von TeamsUpgradePolicy erstellen, um das Clientverhalten zu steuern. 

Erstellen Sie im lokalen PowerShell-Fenster eine neue Instanz von TeamsUpgradePolicy mit NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Weisen Sie dann mithilfe desselben lokalen PowerShell-Fensters diese neue Richtlinie den gewünschten Benutzern zu:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Besprechungsmigration

Wenn ein Benutzer in den TeamsOnly-Modus migriert wird, werden standardmäßig die vorhandenen Skype for Business-Besprechungen, die er organisiert hat, in Teams konvertiert. Sie können das Standardverhalten optional deaktivieren, wenn Sie einem Benutzer den TeamsOnly-Modus zuweisen. Beim Verschieben von Benutzern aus lokalen Besprechungen müssen Besprechungen in die Cloud migriert werden, damit sie mit dem Onlinebenutzerkonto funktionieren. Wenn Sie jedoch "-MoveToTeams" nicht angeben, werden die Besprechungen als Skype for Business-Besprechungen migriert und nicht in Teams konvertiert. 

Beim Zuweisen des TeamsOnly-Modus auf Mandantenebene wird die Besprechungsmigration für keine Benutzer ausgelöst. Wenn Sie den TeamsOnly-Modus auf Mandantenebene zuweisen und Besprechungen migrieren möchten, können Sie powerShell verwenden, um eine Liste der Benutzer im Mandanten zu erhalten (z. B. Get-CsOnlineUser mit den benötigten Filtern zu verwenden), und dann jeden dieser Benutzer durchschleifen, um die Besprechungsmigration mithilfe von Start-CsExMeetingMigration auszulösen. Details finden Sie unter [Verwenden des Besprechungsmigrationsdiensts (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Verwandte Links

[Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungsmigrationsdiensts (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)