---
title: Übersicht über PowerShell für Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Erfahren Sie, wie Sie die PowerShell-Steuerelemente zum Verwalten von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20e85b2f45977a0a78d0d358c2e8aaa01b9257e4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235131"
---
# <a name="teams-powershell-overview"></a>Übersicht über PowerShell für Microsoft Teams

Microsoft Teams verfügt über eine umfangreiche Sammlung von Tools für IT-Administratoren zum Verwalten des Produkts über das Microsoft Teams Admin Center, durch PowerShell-Steuerelemente und Graph-APIs. In diesem Leitfaden wird erläutert, wie wir die PowerShell-Cmdlets für IT-Administratoren strukturieren und er bietet zudem Querverweise zu weiteren Dokumentationen. Beachten Sie, dass die Administratorrollen verschiedener Teams Zugriff auf verschiedene Cmdlets haben. Weitere Informationen finden Sie unter [Verwalten von Teams mittels Administratorrollen für Microsoft Teams](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Welche Module müssen Sie benutzen?

Die PowerShell-Steuerelemente für die Verwaltung von Teams befinden sich in zwei unterschiedlichen PowerShell-Modulen: 
- [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/): das Team PowerShell-Modul enthält alle Cmdlets, die Sie zum Erstellen und Verwalten von Teams benötigen.  
- [Skype for Business PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366): im Skype for Business PowerShell-Modul sind die Cmdlets zum Verwalten von Richtlinien, Konfigurationen und andere Teams-Tools enthalten. 

Die Referenzdokumentation zu den PowerShell-Steuerelementen informiert Sie, welches Modul das Cmdlet enthält, das Sie untersuchen. (In der Zukunft werden die beiden Module kombiniert.)

## <a name="what-can-each-admin-role-do"></a>Was kann jede Administratorrolle tun?

Lesen Sie [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md), um zu verstehen, welche PowerShell-Cmdlets unterschiedliche Administratorrollen nutzen können.

## <a name="creating-and-managing-teams-via-powershell"></a>Erstellen und Verwalten von Teams mittels PowerShell

Die Cmdlets für das Erstellen und Verwalten von Teams befinden sich im [PowerShell-Modul von Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/). 

Teams basieren auf O365-Gruppen. Wenn Sie also ein Team erstellen, erstellen Sie eine Gruppe. Es gibt eine Reihe von Cmdlets für das Arbeiten mit dem Core-Team und dessen Einstellungen(``new-team``, ``get-team``,  ``set-team``), zum Verwalten von Team-Benutzern (``add-teamuser``, ``remove-teamuser``) sowie Cmdlets für die Verwaltung der Kanäle des Teams (``new-teamchannel``. ``remove-teamchannel``). Alle diese Cmdlets können als Endbenutzer ausgeführt werden, Sie funktionieren jedoch nur für die Teams, die Sie besitzen oder deren Mitglied Sie sind. Wenn Sie ein globaler Administrator oder Teams-Dienstadministrator sind, können Sie auf alle Teams in Ihrer Organisation zugreifen.

> Die im Microsoft Teams PowerShell-Modul-Cmdlets verwendete **GroupID** entspricht der im Exchange PowerShell-Modul zurückgegebenen **Identitätseigenschaft**, die auf den Befehl ``Get-UnifiedGroup`` hin zurückgegeben wird.

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>Unterschiede zwischen Vorschau und allgemein verfügbarem PowerShell-Modul von Microsoft Teams

Als wir die allgemein verfügbare Version des PowerShell-Moduls veröffentlicht haben, wurden einige Cmdlets ausschließlich im Beta-Modul beibehalten, wie in der nachstehenden Tabelle beschrieben.

| Cmdlet | In Vorschau verfügbar | Verfügbar in 1.0 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | Ja | Ja |
| Connect-MicrosoftTeams | Ja | Ja |
| Disconnect-MicrosoftTeams | Ja | Ja |
| Get-Team | Ja | Ja |
| Get-TeamChannel | Ja | Ja |
| Get-TeamFunSettings | Nur vor Version 1.0 | Nein |
| Get-TeamGuestSettings | Nur vor Version 1.0 | Nein |
| Get-TeamHelp | Ja | Ja |
| Get-TeamMemberSettings | Nur vor Version 1.0 | Nein |
| Get-TeamMessagingSettings | Nur vor Version 1.0 | Nein |
| Get-TeamUser | Ja | Ja |
| New-Team | Ja | Ja |
| New-TeamChannel | Ja | Ja |
| Remove-Team | Ja | Ja |
| Remove-TeamChannel | Ja | Ja |
| Remove-TeamUser | Ja | Ja |
| Set-Team | Ja | Ja |
| Set-TeamChannel | Ja | Ja |
| Set-TeamFunSettings | Nur vor Version 1.0 | Nein |
| Set-TeamGuestSettings | Nur vor Version 1.0 | Nein |
| Set-TeamMemberSettings | Nur vor Version 1.0 | Nein |
| Set-TeamMessagingSettings | Nur vor Version 1.0 | Nein |
| Set-TeamPicture | Ja | Geplant |


## <a name="managing-policies-via-powershell"></a>Verwalten von Richtlinien mithilfe von PowerShell

Die Cmdlets für die Verwaltung von Richtlinien [sind im Skype for Business-Cmdlet-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366) zu finden.

Eine Richtlinie ist eine Gruppe von Einstellungen, die auf einzelne Benutzer granular angewendet werden kann. Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Erstellen, Anzeigen, Löschen und Aktualisieren von Richtlinien selbst und zum anschließenden Zuweisen dieser Richtlinien zu Benutzern. Die allgemeine Struktur lautet:

- GET-Befehle (z.B.: ``Get-CsTeamsMeetingPolicy``): Geben die Richtliniendokumente, die Ihnen zur Zuweisung in Ihrer Organisation zur Verfügung stehen, zurück. Dies umfasst sowohl Richtlinien, die von Microsoft erstellt und Ihnen zur Verwendung überlassen wurden sowie auch eigene Richtlinien, die Sie erstellt haben.
   > Wenn Sie nur nach den in Ihrer Organisation erstellten benutzerdefinierten Richtlinien suchen möchten, können Sie dazu ``-Filter "tag:*"`` verwenden.

- NEW Befehle (z.B.: ``New-CsTeamsMeetingPolicy``): lassen Sie neue Richtlinien für Ihre Organisation erstellen, die Ihnen dann zur Zuweisung an Nutzer zur Verfügung stehen. Nicht jede Richtlinie unterstützt die Erstellung von benutzerdefinierten Richtlinien. Häufig ist dies der Fall, um sicher zu stellen, dass die Richtlinien, die Sie in Ihrer Organisation verwenden, eine unterstützte Kombination von Einstellungen aufweisen.

- SET-Befehle (z.B. ``Set-CsTeamsMeetingPolicy``): ermöglichen es Ihnen, einer Richtlinie bestimmte Werte zuzuweisen. Einige Richtlinien verfügen nicht über SET-Befehle oder Sie enthalten keine Parameter, die angepasst werden könnten. Jede PowerShell-Beschreibung gibt an, welche Parameter nicht angepasst werden können. 
   > Wenn Sie die Richtlinie bearbeiten möchten, die denjenigen Benutzern in Ihrer Organisation standardmäßig zugewiesen wird, denen keine benutzerdefinierte Richtlinie zugewiesen wurde, führen Sie ``Set-Cs<PolicyName> -Identity Global`` aus.

- REMOVE-Befehle (z.B.: ``Remove-CsTeamsMeetingPolicy``): Sie können dieses Cmdlet verwenden, um eine benutzerdefinierte Richtlinie zu löschen, die in Ihrem Mandanten erstellt wurde. Wenn Sie eine benutzerdefinierte Richtlinie löschen, die mindestens einem Benutzer in Ihrer Organisation zugewiesen wurde, wird diesem Benutzer die globale Richtlinie zugewiesen.
   > Sie können die globale Richtlinie in Ihrer Organisation zwar nicht entfernen, aber wenn Sie die globale Richtlinie in Ihrer Organisation auf die von Microsoft bereitgestellten Standardeinstellungen zurücksetzen möchten, können Sie dazu ``Remove-Cs<PolicyName> -Identity Global`` ausführen.

- GRANT-Befehle (z.B.: ``Grant-CsTeamsMeetingPolicy``): ermöglicht es Ihnen, einem bestimmten Benutzer eine Richtlinie zuzuweisen.
   > Wenn Sie die Zuweisung einer benutzerdefinierten Richtlinie entfernen möchten und die betroffenen Benutzer auf die Standardrichtlinie zurücksetzen möchten, führen Sie ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` aus.

> [!TIP]
> Nicht alle Richtlinien lassen es zu, benutzerdefinierte Richtlinien zu erstellen und einige Richtlinien weisen Einstellungen auf, die nicht angepasst werden können (Sie können die Einstellung einsehen, aber während ``set-`` und ``new-`` keine benutzerdefinierten Werte festlegen). In der Dokumentation des spezifischen Cmdlets ist es angemerkt, falls die Parameter für Kunden nicht verfügbar sind.

Allgemeine Parameter:

- **Identität**: Für ``Get-``, ``Set-``, ``New-`` und ``Remove-``, verweist der Parameter **Identität** immer auf eine spezifische Richtlinieninstanz. Für ``Grant`` verweist der Parameter **Identität** auf ein spezifisches Benutzerobjekt, auf das die Richtlinie angewendet wird.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Verwalten von Konfigurationen mithilfe von PowerShell

Die Cmdlets für die Verwaltung Ihrer Konfiguration sind im [Skype for Business-Cmdlet-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366) zu finden.

Konfigurationen sind im Dienst verwaltete Buckets von Einstellungen, die nicht auf Benutzerebene festgelegt werden können. Einstellungen gelten immer für die gesamte Organisation. Ihre globale Konfiguration ist die einzige effektive Konfiguration in Ihrer Organisation. Jeder Konfigurationstyp enthält zwei primäre Cmdlets:

- ``Get-Cs<ConfigurationName>`` (z.B.: ``Get-CsTeamsClientConfiguration``): 

- SET-Befehle (z.B.: ``Set-CsTeamsClientConfiguration``) Festlegen von Eigenschaften in der Konfiguration dieses Typs. Geben Sie die zu ändernden Parameter an.
   > Sie können auf eine von zwei Arten auf die zu ändernde Konfiguration verweisen: indem Sie **Identity Global** spezifizieren oder indem Sie ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>`` ausführen.

## <a name="other-powershell-tools"></a>Andere PowerShell-Tools

Detaillierte Anweisungen zur Verwendung aller PowerShell-Steuerelemente zum Verwalten von Microsoft Teams und Skype for Business, einschließlich detaillierter Beschreibungen der Einstellungen in jeder Richtlinie, finden Sie in der [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps) und der [Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Teams Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype for Business Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
