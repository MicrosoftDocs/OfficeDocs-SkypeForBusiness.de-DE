---
title: Tools für das Upgrade auf Teams upgraden von Skype for Business lokalen Bereitstellung
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Tools für das Upgrade von Skype for Business auf Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5560373705a12c3d3f1a03c657e8e5bd3565a55
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613424"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Tools für das Upgrade auf Teams &mdash; FÜR IT-Administratoren

In diesem Artikel werden Tools für das Upgrade auf Teams Von Skype for Business. 

Vor Beginn des Upgrades empfiehlt Microsoft die folgenden Artikel, in denen wichtige Upgradekonzepte und Koexistenzverhalten beschrieben werden:

- [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Tools zum Verwalten des Upgrades

Unabhängig von der von Ihnen verwendeten Upgrademethode verwalten Sie für Benutzer, die bereits über Skype for Business Online verfügen, den Übergang zu TeamsOnly mithilfe von [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)das den Koexistenzmodus eines Benutzers steuert. Benutzer mit einem lokalen Konto in Skype for Business Server außerdem mit in `Move-CsUser` [die Cloud verschieben.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Weitere Informationen zu den einzelnen Modi finden Sie unter [Koexistenzmodi.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Wenn Sie derzeit Skype for Business Online Connector zum Verwalten Ihrer Dienste verwenden, müssen Sie zum Teams PowerShell-Modul wechseln und die vorhandenen PowerShell-Skripts aktualisieren. Weitere Informationen finden Sie Skype for Business Wechseln vom [Onlineconnector zum Teams PowerShell-Modul.](teams-powershell-move-from-sfbo.md)

Unabhängig davon, ob Sie einen Umstieg auf ausgewählte Funktionen mithilfe von Skype for Business-Modi durchführen oder einfach von der Standardkonfiguration "Islands" auf denOnly-Modus upgraden, ist TeamsUpgradePolicy das primäre Tool. Wie jede andere Richtlinie in Teams können Sie TeamsUpgradePolicy direkt einem Benutzer zuweisen. Sie können die Richtlinie auch als mandantenweite Standardrichtlinie festlegen. Jede Zuweisung an einen Benutzer hat Vorrang vor der Standardeinstellung des Mandanten.  Sie können die Richtlinie in der Teams und in PowerShell verwalten.

Sie können einen beliebigen Modus von TeamsUpgradePolicy, mit Ausnahme des TeamsOnly-Modus, Benutzern zuweisen, die Skype for Business lokal heimisch sind. Umgekehrt kann Benutzern, die in der Cloud gespeichert sind, nur der TeamsOnly-Modus zugewiesen werden. **Der "TeamsOnly"-Modus** kann nur einem Benutzer zugewiesen werden, der bereits in der Cloud gespeichert ist, da Inaktivität und Verbund mit Skype for Business-Benutzern sowie Microsoft 365 Telefonsystem-Funktionen nur möglich sind, wenn der Benutzer in Skype for Business Online gespeichert ist.  Außerdem können Sie den **TeamsOnly-Modus** nicht als mandantenweite Standardbereitstellung zuweisen, wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen (die durch das Vorhandensein eines lyncdiscover-DNS-Eintrags erkannt wird, der auf einen anderen Speicherort als Office 365 verweist. Details finden Sie unter [Deaktivieren der Hybridkonfiguration, um die Migration zu nur Teams abschließen.](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)

Benutzer mit Skype for Business konten, die lokal homed sind, müssen [online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) in den Teams Nur-Modus mit Move-CsUser im lokalen Skype for Business Toolset verschoben werden. 

Im Gegensatz zu anderen Richtlinien ist es nicht möglich, neue Instanzen von TeamsUpgradePolicy in Microsoft 365 oder Office 365. Alle vorhandenen -Instanzen sind in den Dienst integriert.  (Beachten Sie, dass der Modus eine Eigenschaft in TeamsUpgradePolicy und nicht der Name einer Richtlinieninstanz ist.) In einigen – aber nicht allen – Fällen ist der Name der Richtlinieninstanz mit dem Modus identisch. Insbesondere, wenn Sie einem Benutzer den TeamsOnly-Modus zuweisen möchten, weisen Sie diesem Benutzer die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu. Um eine Liste aller Instanzen zu sehen, können Sie den folgenden Befehl ausführen:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Um einen Onlinebenutzer in den TeamsOnly-Modus zu aktualisieren, weisen Sie die Instanz "UpgradeToTeams" zu: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Zum Aktualisieren eines lokalen Skype for Business-Benutzers in den TeamsOnly-Modus verwenden Move-CsUser im lokalen Toolset:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

Führen Sie den folgenden Befehl aus, um den Modus für alle Benutzer im Mandanten zu ändern, mit Ausnahme der Benutzer mit einer expliziten Benutzerzuteilung (die Vorrang hat):

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Wenn Sie benutzer mit lokalen Skype for Business haben, können Sie teamsOnly-Modus nicht auf Mandantenebene zuweisen. Sie müssen diese Benutzer einzeln in den Teams mit Move-CsUser verschieben.


## <a name="using-notifications-in-skype-for-business-clients"></a>Verwenden von Benachrichtigungen auf Skype for Business Clients

Administratoren haben die Möglichkeit, im Skype for Business-Client Endbenutzerbenachrichtigungen zur Verfügung zu stellen, um die Benutzer darüber zu informieren, dass sie in Kürze auf Teams aktualisiert werden, wie in der folgenden Abbildung dargestellt. So möchte der Administrator beispielsweise eine Woche vor dem Plan, eine Benutzergruppe in denOnly-Modus zu aktualisieren, diese Benachrichtigungen für diese Benutzergruppe aktivieren. Diese Benachrichtigungen werden mithilfe einer Instanz von TeamsUpgradePolicy mit NotifySfbUsers=true aktiviert.  Für alle Modi, bei denen es sich nicht um TeamsOnly handelt, gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entspricht.  Für alle Modi, bei denen es sich nicht um TeamsOnly handelt, gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entspricht. 

![Diagramm mit Benachrichtigungen](media/teams-upgrade-sfb-with-notifications.png)

Wenn Ihre Benutzer in Skype for Business Online zu Hause sind, weisen Sie einfach die Richtlinieninstanz zu, die denselben Modus wie der Benutzer hat, jedoch mit NotifySfbUsers=true. 

Wenn Ihre Benutzer in Skype for Business Server lokal zu Hause sind, müssen Sie das lokale Toolset verwenden, und Sie benötigen Skype for Business Server 2019 oder CU8 für Skype for Business Server 2015. Für benutzer, die in Skype for Business Server lokal homed sind, wird die Moduseigenschaft von der Onlineinstanz von TeamsUpgradePolicy berücksichtigt, die NotifySfbUsers-Eigenschaft jedoch nicht. Wenn Benachrichtigungen gewünscht werden, müssen Sie eine lokale Instanz von TeamsUpgradePolicy erstellen, um das Clientverhalten zu steuern. 

Erstellen Sie im lokalen PowerShell-Fenster eine neue Instanz von TeamsUpgradePolicy mit NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Weisen Sie dann im gleichen lokalen PowerShell-Fenster den gewünschten Benutzern diese neue Richtlinie zu:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Besprechungsmigration

Wenn ein Benutzer in den TeamsOnly-Modus migriert wird, werden seine vorhandenen Skype for Business, die er organisiert hat, standardmäßig in andere Teams. Sie können das Standardverhalten optional deaktivieren, wenn Sie einem Benutzer den TeamsOnly-Modus zuweisen. Beim Verschieben von Benutzern aus der lokalen Bereitstellung müssen Besprechungen in die Cloud migriert werden, damit sie mit dem Onlinebenutzerkonto funktionieren. Wenn Sie aber -MoveToTeams nicht angeben, werden die Besprechungen als Skype for Business-Besprechungen migriert und nicht in ein Teams konvertiert. 

Beim Zuweisen des TeamsOnly-Modus auf Mandantenebene wird die Besprechungsmigration für keine Benutzer ausgelöst. Wenn Sie TeamsOnly-Modus auf Mandantenebene zuweisen und Besprechungen migrieren möchten, können Sie PowerShell verwenden, um eine Liste der Benutzer im Mandanten zu erhalten (z. B. mithilfe von Get-CsOnlineUser mit den erforderlichen Filtern), und dann jeden dieser Benutzer in einer Schleife durch schleifen, um die Besprechungsmigration mit Start-CsExMeetingMigration auszulösen. Details finden Sie unter [Verwenden von Meeting Migration Service (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Links zu verwandten Themen

[Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
