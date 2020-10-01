---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Teams – Tools für das Upgrade
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 076e96ac8cf44e05e2852ca5bdf33b42e14eb731
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328194"
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

Je nachdem, welche Upgrade-Methode Sie wählen, verwalten Sie für Benutzer, die bereits Skype for Business Online haben, den Übergang zu TeamsOnly mithilfe von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), der den Koexistenzmodus eines Benutzers steuert. Für Benutzer mit einem lokalen Konto in Skype for Business Server verwenden Sie auch, `Move-CsUser` um Sie in [die Cloud zu verschieben](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Weitere Informationen zu den einzelnen Modi finden Sie unter [Koexistenz Modi](migration-interop-guidance-for-teams-with-skype.md).  

Unabhängig davon, ob Sie über den Skype for Business-Modus einen Übergang zur Auswahlfunktion ausführen oder einfach über die standardmäßige Konfiguration der Inseln auf den TeamsOnly-Modus umsteigen, ist TeamsUpgradePolicy das wichtigste Tool für Benutzer, die bereits Skype for Business Online haben. Wie bei allen anderen Richtlinien in Teams können Sie TeamsUpgradePolicy einem Benutzer direkt zuweisen. Sie können die Richtlinie auch als Mandantenweite Standardeinstellung festlegen. Jede Zuordnung zu einem Benutzer hat Vorrang vor der Standardeinstellung Mandanten.  Sie können die Richtlinie in der Team-Verwaltungskonsole und in PowerShell verwalten.

Sie können den Benutzern, die in Skype for Business lokal gehostet werden, auch einen beliebigen TeamsUpgradePolicy-Modus (mit Ausnahme des TeamsOnly-Modus) zuweisen. Der **TeamsOnly-Modus kann nur einem Nutzer zugewiesen werden, der sich bereits in Skype for Business Online befindet**. Dies liegt daran, dass Interop mit Skype for Business-Benutzern und-Föderation sowie Microsoft 365-Telefon System Funktionen nur möglich ist, wenn der Benutzer in Skype for Business Online verwaltet wird. Darüber hinaus **können Sie den TeamsOnly-Modus nicht als mandantenübergreifenden Standardwert zuweisen, wenn Sie über eine lokale Skype for Business-Bereitstellung verfügen** (die durch Anwesenheit eines lyncdiscover-DNS-Eintrags erkannt wird, der auf einen anderen Speicherort als Office 365 verweist.

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
>Wenn Sie über Benutzer mit Skype for Business-Konten lokal verfügen, können Sie den TeamsOnly-Modus auf Mandantenebene nicht zuweisen. Sie müssen diese Benutzer mithilfe von Move-CsUser einzeln in die Cloud verschieben.


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

