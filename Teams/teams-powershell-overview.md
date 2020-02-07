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
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die PowerShell-Steuerelemente für die Verwaltung von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d22eb0b14d25bec57949bb804e8bb8098ee33510
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836955"
---
# <a name="teams-powershell-overview"></a>Übersicht über PowerShell für Microsoft Teams

Microsoft Teams verfügt über eine umfangreiche Reihe von Tools für IT-Administratoren, um das Produkt über das Microsoft Teams Admin Center, PowerShell-Steuerelemente und Diagramm-APIs zu verwalten. In diesem Leitfaden wird erläutert, wie wir unsere PowerShell-Cmdlets für IT-Administratoren strukturieren und Verweise auf weitere Dokumentationen bereitstellen. Beachten Sie, dass verschiedene Teams-Administratorrollen Zugriff auf verschiedene Cmdlets haben. Weitere Informationen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Welche Module müssen Sie verwenden?

Die PowerShell-Steuerelemente für die Verwaltung von Teams sind in zwei verschiedenen PowerShell-Modulen zu finden: 
- [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/) : Das PowerShell-Modul von Teams enthält alle Cmdlets, die Sie zum Erstellen und Verwalten von Teams benötigen.  
- [Skype for Business PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366): das Skype for Business PowerShell-Modul enthält die Cmdlets zum Verwalten von Richtlinien, Konfigurationen und anderen Tools für Teams. 

In der Referenzdokumentation zu den PowerShell-Steuerelementen erfahren Sie, welches Modul das Cmdlet enthält, das Sie untersuchen. (Schließlich werden die beiden Module kombiniert.)

## <a name="what-can-each-admin-role-do"></a>Was kann jede Administratorrolle tun?

Lesen [verwenden Sie Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md) , um zu verstehen, welche PowerShell-Cmdlets von verschiedenen Administratorrollen genutzt werden können.

## <a name="creating-and-managing-teams-via-powershell"></a>Erstellen und Verwalten von Teams über PowerShell

Die Cmdlets zum Erstellen und Verwalten von Teams befinden sich im [PowerShell-Modul von Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/). 

Teams werden von Office 365-Gruppen gesichert, sodass Sie beim Erstellen eines Teams eine Gruppe erstellen. Es gibt eine Reihe von Cmdlets, die für das Funktionieren des Kernteams und dessen``new-team``Einstellungen ``get-team``( ``set-team``,,), Verwalten von``add-teamuser``Team ``remove-teamuser``Benutzern (,) sowie Cmdlets für die Verwaltung der Kanäle des Teams (``new-teamchannel``, ``remove-teamchannel``) bereitgestellt werden. Alle diese Cmdlets können als Endbenutzer ausgeführt werden, funktionieren aber nur in den Teams, denen Sie angehören oder deren Mitglied Sie sind. Wenn Sie ein globaler Administrator oder Team Dienst Administrator sind, können Sie auf alle Teams in Ihrer Organisation zugreifen.

> Die in den Microsoft Teams PowerShell-Modul-Cmdlets verwendete **Gruppen** -ID ist mit der im Exchange PowerShell ``Get-UnifiedGroup`` -Modul zurückgegebenen **Identity** -Eigenschaft identisch.

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>Unterschiede zwischen Preview und im allgemeinen verfügbaren Microsoft Teams PowerShell-Modul

Als wir unsere allgemein verfügbare Version unseres PowerShell-Moduls veröffentlichten, blieben einige Cmdlets im Beta-only-Modul wie in der nachstehenden Tabelle beschrieben.

| Cmdlet | In der Vorschau verfügbar | Verfügbar in 1,0 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | Ja | Ja |
| Connect-Microsoft Teams | Ja | Ja |
| Trennen-Microsoft Teams | Ja | Ja |
| Get-Team | Ja | Ja |
| Get-TeamChannel | Ja | Ja |
| Get-TeamFunSettings | Vor der 1,0-Version | Nein |
| Get-TeamGuestSettings | Vor der 1,0-Version | Nein |
| Get-TeamHelp | Ja | Ja |
| Get-TeamMemberSettings | Vor der 1,0-Version | Nein |
| Get-TeamMessagingSettings | Vor der 1,0-Version | Nein |
| Get-TeamUser | Ja | Ja |
| Neues Team | Ja | Ja |
| Neu – TeamChannel | Ja | Ja |
| Remove-Team | Ja | Ja |
| Remove-TeamChannel | Ja | Ja |
| Remove-TeamUser | Ja | Ja |
| Team einrichten | Ja | Ja |
| Satz-TeamChannel | Ja | Ja |
| Satz-TeamFunSettings | Vor der 1,0-Version | Nein |
| Satz-TeamGuestSettings | Vor der 1,0-Version | Nein |
| Satz-TeamMemberSettings | Vor der 1,0-Version | Nein |
| Satz-TeamMessagingSettings | Vor der 1,0-Version | Nein |
| Satz-TeamPicture | Ja | Nein, geplant |


## <a name="managing-policies-via-powershell"></a>Verwalten von Richtlinien über PowerShell

Die Cmdlets für die Verwaltung von Richtlinien sind im [Skype for Business-Cmdlet-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366)zu finden.

> [!NOTE]
> Die Cmdlets sind in ihrer PowerShell-Sitzung verfügbar, nachdem Sie eine Verbindung mit Skype for Business Online hergestellt haben. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell). 

Bei einer Richtlinie handelt es sich um eine Gruppe von Einstellungen, die auf einzelne Benutzer Granular angewendet werden können. Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Erstellen, anzeigen, löschen und Aktualisieren der Richtlinien selbst und zum Zuweisen dieser Richtlinien zu Benutzern. Die allgemeine Struktur lautet:

- Abrufen von Befehlen (beispielsweise ``Get-CsTeamsMeetingPolicy``): Geben Sie die Richtliniendokumente zurück, die für Sie in Ihrer Organisation zur Verfügung stehen, sowohl die von Microsoft für Sie erstellten Richtlinien als auch die von Ihnen erstellten benutzerdefinierten Richtlinien.
   > Wenn Sie nur die benutzerdefinierten Richtlinien finden möchten, die Sie in Ihrer Organisation erstellt haben, ``-Filter "tag:*"``können Sie Sie verwenden.

- Neue Befehle (beispielsweise ``New-CsTeamsMeetingPolicy``): Sie können neue Richtlinien für Ihre Organisation erstellen, die dann Benutzern in Ihrer Organisation zugewiesen werden können. Nicht alle Richtlinien unterstützen das Erstellen benutzerdefinierter Richtlinien. Häufig wird dadurch sichergestellt, dass die in Ihrer Organisation verwendeten Richtlinien eine unterstützte Kombination von Einstellungen aufweisen.

- Festlegen von Befehlen (beispielsweise ``Set-CsTeamsMeetingPolicy``): Hiermit können Sie bestimmte Werte für eine bestimmte Richtlinie festlegen. Für einige Richtlinien sind keine festgelegten Befehle verfügbar, oder es sind keine Parameter enthalten, die in der Richtlinie nicht angepasst werden können. Jede PowerShell-Beschreibung gibt an, welche Parameter nicht angepasst werden können. 
   > Wenn Sie die Richtlinie bearbeiten möchten, die standardmäßig Benutzern in Ihrer Organisation zugewiesen wird, denen keine benutzerdefinierte Richtlinie zugewiesen ``Set-Cs<PolicyName> -Identity Global``ist, führen Sie Sie aus.

- Entfernen von Befehlen (beispielsweise ``Remove-CsTeamsMeetingPolicy``): Sie können dieses Cmdlet verwenden, um eine benutzerdefinierte Richtlinie zu löschen, die in Ihrem Mandanten erstellt wurde. Wenn Sie eine benutzerdefinierte Richtlinie löschen, die mindestens einem Benutzer in Ihrer Organisation zugewiesen wurde, wird dieser Benutzer auf die globale Richtlinie zurückgreifen.
   > Sie können die globale Richtlinie in Ihrer Organisation nicht wirklich entfernen, aber wenn Sie die globale Richtlinie in Ihrer Organisation auf die von Microsoft bereitgestellten Standardeinstellungen zurück ``Remove-Cs<PolicyName> -Identity Global``setzen möchten, können Sie ausführen.

- Grant-Befehl (beispielsweise ``Grant-CsTeamsMeetingPolicy``): Hiermit können Sie einem bestimmten Benutzer eine Richtlinie zuweisen.
   > Um eine benutzerdefinierte Richtlinienzuweisung zu entfernen und den Benutzer auf die Standardrichtlinie in Ihrer Organisation zurückgreifen zu ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``lassen, führen Sie.

> [!TIP]
> Nicht alle Richtlinien ermöglichen das Erstellen benutzerdefinierter Richtlinien, und einige Richtlinien verfügen über Einstellungen, die Sie nicht anpassen können (sodass Sie die Einstellung anzeigen, ``set-`` aber ``new-``keinen benutzerdefinierten Wert während und festlegen können). Die Dokumentation des jeweiligen Cmdlets Ruft ab, wenn Parameter nicht für die Verwendung durch Kunden verfügbar sind.

Allgemeine Parameter:

- **Identity**: für ``Get-``, ``Set-``, ``New-``, und ``Remove-``der Parameter **Identity** bezieht sich immer auf eine bestimmte Richtlinieninstanz. ``Grant``Der Parameter **Identity** bezieht sich auf ein bestimmtes Benutzerobjekt, auf das die Richtlinie angewendet wird.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Verwalten von Konfigurationen über PowerShell

Die Cmdlets für die Verwaltung Ihrer Konfiguration sind im [Skype for Business-Cmdlet-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366)zu finden.

Konfigurationen sind Buckets von Einstellungen, die im Dienst verwaltet werden und nicht auf Benutzerebene angegeben werden können. Einstellungen gelten immer für die gesamte Organisation. Ihre globale Konfiguration ist die einzige effektive Konfiguration in Ihrer Organisation. Jeder Konfigurationstyp enthält zwei primäre Cmdlets:

- ``Get-Cs<ConfigurationName>``(Beispiel: ``Get-CsTeamsClientConfiguration``): 

- Befehlssatz (beispielsweise ``Set-CsTeamsClientConfiguration``): legt Eigenschaften in der Konfiguration dieses Typs fest. Geben Sie die Parameter an, die Sie ändern möchten.
   > Sie können auf die zu ändernde Konfiguration auf eine von zwei Arten verweisen: durch Angeben von-**Identity Global**oder durch Ausführen ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Andere PowerShell-Tools

Ausführliche Anweisungen zur Verwendung aller PowerShell-Steuerelemente für die Verwaltung von Microsoft Teams und Skype for Business, einschließlich detaillierter Beschreibungen der Einstellungen in den einzelnen Richtlinien, finden Sie in der [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps) und in der [Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
