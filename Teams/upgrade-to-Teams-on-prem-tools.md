---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940642"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Tools für das Upgrade auf Teams &mdash; für IT-Administratoren

In diesem Artikel werden Tools für das Upgrade auf Teams beschrieben. Dieser Artikel ist der dritte von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.  

- [Übersicht](upgrade-to-teams-on-prem-overview.md)
- [Upgrade-Methoden](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Tools zum Verwalten des Upgrades**   (dieser Artikel)
- [Weitere Überlegungen für Organisationen mit Skype for Business lokal](upgrade-to-teams-on-prem-considerations.md)
- [Implementieren des Upgrades](upgrade-to-teams-on-prem-implement.md)
- [Überlegungen zum Public Switched Telephone Network (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:

- [Koexistenz von Teams und Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Koexistenzmodus – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Tools für die Verwaltung des Upgrades

Unabhängig von der gewählten Aktualisierungsmethode verwalten Sie den Übergang zu TeamsOnly mithilfe von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), der den Koexistenzmodus eines Benutzers steuert. Weitere Informationen zu den einzelnen Modi finden Sie unter [Koexistenz Modi](migration-interop-guidance-for-teams-with-skype.md).

Unabhängig davon, ob Sie über den Skype for Business-Modus einen Übergang zur Auswahlfunktion ausführen oder einfach von der Standardkonfiguration der Inseln auf den TeamsOnly-Modus umsteigen, ist TeamsUpgradePolicy das wichtigste Tool. Wie bei allen anderen Richtlinien in Teams können Sie TeamsUpgradePolicy einem Benutzer direkt zuweisen. Sie können die Richtlinie auch als Mandantenweite Standardeinstellung festlegen. Jede Zuordnung zu einem Benutzer hat Vorrang vor der Standardeinstellung Mandanten.  Sie können die Richtlinie in der Team-Verwaltungskonsole und in PowerShell verwalten.

Sie können Benutzern jede Art von TeamsUpgradePolicy zuweisen, unabhängig davon, ob sich der Benutzer in Skype for Business Online oder lokal befindet, **mit der Ausnahme, dass der TeamsOnly-Modus nur einem Nutzer zugewiesen werden kann, der bereits in Skype for Business Online ist**. Dies liegt daran, dass Interop mit Skype for Business-Benutzern und-Föderation sowie Microsoft 365-Telefon System Funktionen nur möglich ist, wenn der Benutzer in Skype for Business Online verwaltet wird.

Benutzer mit Skype for Business-Konten, die sich lokal [benetzen, müssen](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) mit Move-CsUser im lokalen Skype for Business-Toolset Online (entweder in Skype for Business Online oder direkt an Teams) verschoben werden. Diese Benutzer können in 1 oder 2 Schritten in TeamsOnly verschoben werden:

-   1 Schritt: Geben Sie den Schalter-MoveToTeams in Move-CsUser an. Hierfür ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 oder höher erforderlich.

-   2 Schritte: Nachdem Sie Move-CsUser ausgeführt haben, gewähren Sie dem Benutzer den TeamsOnly-Modus mithilfe von TeamsUpgradePolicy.

Im Gegensatz zu anderen Richtlinien ist es nicht möglich, neue Instanzen von TeamsUpgradePolicy in Microsoft 365 oder Office 365 zu erstellen. Alle vorhandenen Instanzen sind in den Dienst integriert.  (Beachten Sie, dass Mode eine Eigenschaft in TeamsUpgradePolicy und nicht der Name einer Richtlinieninstanz ist.) In einigen-aber nicht in allen Fällen ist der Name der Richtlinieninstanz derselbe wie der Modus. Um einem Benutzer den TeamsOnly-Modus zuzuweisen, erteilen Sie diesem Benutzer die Instanz "UpgradeToTeams" von TeamsUpgradePolicy. Um eine Liste aller Instanzen anzuzeigen, können Sie den folgenden Befehl ausführen:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Wenn Sie einen Online Benutzer auf den TeamsOnly-Modus aktualisieren möchten, weisen Sie die "UpgradeToTeams"-Instanz zu: 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Um einen lokalen Skype for Business-Benutzer in den TeamsOnly-Modus zu aktualisieren, verwenden Sie Move-CsUser im lokalen Toolset:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Führen Sie den folgenden Befehl aus, um den Modus für alle Benutzer im Mandanten zu ändern, mit Ausnahme derjenigen, die über eine explizite pro-Benutzer-Grant (die Vorrang hat) verfügen:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Wenn Sie Benutzer mit Skype for Business-Konten lokal haben, dürfen Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen, es sei denn, Sie weisen allen Benutzern mit lokalen Skype for Business-Konten explizit einen anderen Modus zu.


## <a name="using-notifications-in-skype-for-business-clients"></a>Verwenden von Benachrichtigungen in Skype for Business-Clients

Administratoren können im Skype for Business-Clientbenachrichtigungen für Endbenutzer bereitstellen, um die Benutzer darüber zu informieren, dass Sie in Kürze auf Teams aktualisiert werden, wie in der nachstehenden Abbildung zu sehen ist. Wenn beispielsweise eine Woche vor dem Administrator die Aktualisierung einer Gruppe von Benutzern auf den TeamsOnly-Modus plant, möchte der Administrator diese Benachrichtigungen für diese Benutzergruppe aktivieren. Diese Benachrichtigungen werden mit einer Instanz von TeamsUpgradePolicy mit NotifySfbUsers = true aktiviert.  Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entsprechen.  Für alle anderen Modi als TeamsOnly gibt es tatsächlich zwei Instanzen pro Modus, die den beiden Werten von NotifySfbUsers entsprechen. 

![Diagramm mit Benachrichtigungen](media/teams-upgrade-sfb-with-notifications.png)

Wenn Ihre Benutzer in Skype for Business online gehostet werden, weisen Sie einfach die Richtlinieninstanz zu, die den gleichen Modus wie der Benutzer hat, aber mit NotifySfbUsers = true. 

Wenn Ihre Benutzer in Skype for Business Server lokal gehostet werden, müssen Sie das lokale Toolset verwenden, und Sie benötigen Skype for Business Server 2019 oder CU8 für Skype for Business Server 2015. Für Benutzer, die in Skype for Business Server lokal gehostet werden, wird die Mode-Eigenschaft aus der Online Instanz von TeamsUpgradePolicy berücksichtigt, die NotifySfbUsers-Eigenschaft ist jedoch nicht. Wenn Benachrichtigungen erwünscht sind, müssen Sie eine lokale Instanz von TeamsUpgradePolicy erstellen, um das Clientverhalten zu steuern. 

Erstellen Sie im lokalen PowerShell-Fenster eine neue Instanz von TeamsUpgradePolicy mit NotifySfbUsers = true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Weisen Sie dann mithilfe desselben lokalen PowerShell-Fensters die neue Richtlinie den gewünschten Benutzern zu:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Besprechungs Migration

Wenn ein Benutzer in den TeamsOnly-Modus migriert wird, werden die vorhandenen Skype for Business-Besprechungen, die Sie organisiert haben, standardmäßig in Teams konvertiert. Sie können das Standardverhalten beim Zuweisen des TeamsOnly-Modus zu einem Benutzer optional deaktivieren. Beim Verschieben von Benutzern aus dem lokalen Bereich müssen Besprechungen in die Cloud migriert werden, damit Sie mit dem Online Benutzerkonto funktionieren, aber wenn Sie MoveToTeams nicht angeben, werden die Besprechungen als Skype for Business-Besprechungen migriert und nicht in Teams konvertiert. 

Wenn Sie den TeamsOnly-Modus auf Mandantenebene zuweisen, wird die Besprechungs Migration für keine Benutzer ausgelöst. Wenn Sie den TeamsOnly-Modus auf Mandantenebene zuweisen und Besprechungen migrieren möchten, können Sie mithilfe von PowerShell eine Liste der Benutzer im Mandanten abrufen (beispielsweise die Verwendung von Get-CsOnlineUser mit allen benötigten Filtern) und dann jeden dieser Benutzer durchlaufen, um die Besprechungs Migration mithilfe von Start-CsExMeetingMigration zu starten. Ausführliche Informationen finden Sie unter [Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).



## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

