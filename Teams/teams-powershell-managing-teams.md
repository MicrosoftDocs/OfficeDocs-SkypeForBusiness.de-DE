---
title: Verwalten von Teams mit Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie Microsoft Teams mithilfe von Teams PowerShell verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09d11b2c697ba57ea161d0ce961cf5ba73794617
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852176"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Verwalten von Teams mit Microsoft Teams PowerShell

In diesem Artikel wird gezeigt, wie Sie Microsoft Teams PowerShell zum Verwalten von Teams und Skype for Business verwenden. 

Verwenden Sie diese Richtlinien in Verbindung mit dem [Microsoft Teams-Cmdlet Reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) und dem [Skype for Business-Cmdlet Reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="create-and-manage-teams-using-powershell"></a>Erstellen und Verwalten von Teams mithilfe von PowerShell

Die Cmdlets zum Erstellen und Verwalten von Teams befinden sich im [PowerShell-Modul von Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Teams werden von Office 365-Gruppen gesichert, sodass Sie beim Erstellen eines Teams eine Gruppe erstellen. Es gibt eine Reihe von Cmdlets, die für das Funktionieren des Kernteams und dessen Einstellungen (, ``new-team`` ``get-team`` ,  ``set-team`` ), Verwalten von Team Benutzern ( ``add-teamuser`` , ``remove-teamuser`` ) sowie Cmdlets für die Verwaltung der Kanäle des Teams ( ``new-teamchannel`` , ``remove-teamchannel`` ) bereitgestellt werden. Alle diese Cmdlets können als Endbenutzer ausgeführt werden, funktionieren aber nur in den Teams, denen Sie angehören oder deren Mitglied Sie sind. Wenn Sie ein globaler Administrator oder Team Dienst Administrator sind, können Sie auf alle Teams in Ihrer Organisation zugreifen.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Die in den Microsoft Teams PowerShell-Modul-Cmdlets verwendete **Gruppen** -ID ist mit der im Exchange PowerShell-Modul zurückgegebenen **Identity** -Eigenschaft identisch ``Get-UnifiedGroup`` .

## <a name="manage-policies-via-powershell"></a>Verwalten von Richtlinien über PowerShell

> [!NOTE]
> - Skype for Business Online Connector wird in Teams PowerShell konsolidiert. Sie ist derzeit in der öffentlichen Vorschau verfügbar. In der Zeit sind Skype for Business Online-Cmdlets, die für Teams gelten, nativ im PowerShell-Modul von Teams verfügbar. Installationsschritte finden Sie im PowerShell-Artikel [Installieren von Teams](teams-powershell-install.md) .
>
> - Die Cmdlets sind in ihrer PowerShell-Sitzung verfügbar, nachdem Sie eine Verbindung mit Skype for Business Online hergestellt haben. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Suchen Sie die Cmdlets zum Verwalten von Richtlinien im [Skype for Business-Cmdlet-Modul](https://www.microsoft.com/download/details.aspx?id=39366).

Bei einer Richtlinie handelt es sich um eine Gruppe von Einstellungen, die auf einzelne Benutzer Granular angewendet werden können. Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Erstellen, anzeigen, löschen und Aktualisieren der Richtlinien selbst und zum Zuweisen dieser Richtlinien zu Benutzern. Die allgemeine Struktur lautet:

- **Abrufen** von Befehlen (beispielsweise ``Get-CsTeamsMeetingPolicy`` ): gibt die Richtliniendokumente zurück, die Ihnen in Ihrer Organisation zugewiesen werden können, einschließlich der von Microsoft für Sie erstellten Richtlinien sowie der von Ihnen erstellten benutzerdefinierten Richtlinien.
   - Um nur die benutzerdefinierten Richtlinien zu finden, die Sie in Ihrer Organisation erstellt haben, verwenden Sie ``-Filter "tag:*"`` .

- **Neue** Befehle (beispielsweise ``New-CsTeamsMeetingPolicy`` ): erstellt neue Richtlinien für Ihre Organisation, die Benutzern in Ihrer Organisation zugewiesen werden sollen. Nicht alle Richtlinien unterstützen das Erstellen benutzerdefinierter Richtlinien. Häufig wird dadurch sichergestellt, dass die in Ihrer Organisation verwendeten Richtlinien eine unterstützte Kombination von Einstellungen aufweisen.

- **Festlegen** von Befehlen (beispielsweise ``Set-CsTeamsMeetingPolicy`` ): legt bestimmte Werte für eine bestimmte Richtlinie fest. Bei einigen Richtlinien sind keine festgelegten Befehle verfügbar, oder Sie enthalten Parameter, die in der Richtlinie nicht angepasst werden können. Die PowerShell-Beschreibungen geben an, welche Parameter nicht angepasst werden können. 
   - Wenn Sie die Richtlinie bearbeiten möchten, die standardmäßig Benutzern in Ihrer Organisation zugewiesen wird, denen keine benutzerdefinierte Richtlinie zugewiesen ist, führen Sie Sie aus ``Set-Cs<PolicyName> -Identity Global`` .

- **Entfernen** von Befehlen (beispielsweise ``Remove-CsTeamsMeetingPolicy`` ): Löscht eine benutzerdefinierte Richtlinie, die in Ihrem Mandanten erstellt wurde. Wenn Sie eine benutzerdefinierte Richtlinie löschen, die mindestens einem Benutzer in Ihrer Organisation zugewiesen wurde, wird dieser Benutzer auf die globale Richtlinie zurückgreifen.
   - Sie können die globale Richtlinie in Ihrer Organisation nicht wirklich entfernen, aber wenn Sie die globale Richtlinie in Ihrer Organisation auf die von Microsoft bereitgestellten Standardeinstellungen zurücksetzen möchten, führen Sie ``Remove-Cs<PolicyName> -Identity Global`` .

- **Grant** -Befehl (beispielsweise ``Grant-CsTeamsMeetingPolicy`` ): weist einem bestimmten Benutzer eine Richtlinie zu.
   - Um eine benutzerdefinierte Richtlinienzuweisung zu entfernen und den Benutzer auf die Standardrichtlinie in Ihrer Organisation zurückgreifen zu lassen, führen Sie ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Nicht alle Richtlinien ermöglichen das Erstellen benutzerdefinierter Richtlinien, und einige Richtlinien verfügen über Einstellungen, die Sie nicht anpassen können (sodass Sie die Einstellung anzeigen, aber keinen benutzerdefinierten Wert während und festlegen können ``set-`` ``new-`` ). In der Dokumentation für die einzelnen Cmdlets wird angegeben, ob Parameter für die Verwendung durch Kunden verfügbar sind.

Allgemeine Parameter:

- **Identity** : für ``Get-`` , ``Set-`` ,, ``New-`` und ``Remove-`` der Parameter **Identity** bezieht sich immer auf eine bestimmte Richtlinieninstanz. ``Grant``Der Parameter **Identity** bezieht sich auf ein bestimmtes Benutzerobjekt, auf das die Richtlinie angewendet wird.

## <a name="manage-configurations-via-powershell"></a>Verwalten von Konfigurationen über PowerShell

Suchen Sie die Cmdlets für die Verwaltung Ihrer Konfiguration im [Skype for Business-Cmdlet-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Konfigurationen sind Buckets von Einstellungen, die im Dienst verwaltet werden und nicht auf Benutzerebene angegeben werden können. Einstellungen gelten immer für die gesamte Organisation. Ihre globale Konfiguration ist die einzige effektive Konfiguration in Ihrer Organisation. Jeder Konfigurationstyp enthält zwei primäre Cmdlets:

- ``Get-Cs<ConfigurationName>`` (Beispiel ``Get-CsTeamsClientConfiguration`` :):

- Befehlssatz (beispielsweise ``Set-CsTeamsClientConfiguration`` ): legt Eigenschaften in der Konfiguration dieses Typs fest. Geben Sie die Parameter an, die Sie ändern möchten.
   > Sie können auf die zu ändernde Konfiguration auf eine von zwei Arten verweisen: durch Angeben von- **Identity Global** oder durch Ausführen ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Was kann jede Administratorrolle tun?

Lesen [verwenden Sie Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md) , um zu verstehen, welche Administratorrollen für jedes PowerShell-Cmdlet ausgeführt werden können.

## <a name="related-topics"></a>Verwandte Themen

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Teams PowerShell-Anmerkungen zu dieser Version](teams-powershell-release-notes.md)

[Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md)
