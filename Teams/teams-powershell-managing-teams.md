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
description: Erfahren Sie, wie Sie Microsoft Teams mit Teams PowerShell verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8494f7951a051f95f9b934d04f274a020446b6cd
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617747"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Verwalten von Teams mit Microsoft Teams PowerShell

In diesem Artikel erfahren Sie, wie Sie Microsoft Teams PowerShell zum Verwalten von Teams und Skype for Business verwenden. 

Verwenden Sie diesen Leitfaden in Verbindung mit der [Microsoft Teams-Cmdletreferenz](/powershell/teams/?view=teams-ps) und [der Skype for Business-Cmdletreferenz.](/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Erstellen und Verwalten von Teams mit PowerShell

Die Cmdlets zum Erstellen und Verwalten von Teams befinden sich im [Microsoft Teams PowerShell-Modul.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Teams werden von Office 365-Gruppen unterstützt. Wenn Sie also ein Team erstellen, erstellen Sie eine Gruppe. Es gibt eine Reihe von Cmdlets für den Betrieb im Kernteam und deren Einstellungen ( , , ), Verwalten von Teambenutzern ( , ), sowie ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` Cmdlets ``new-teamchannel`` zum Verwalten der Kanäle des Teams ( , ``remove-teamchannel`` ). Alle diese Cmdlets können als Endbenutzer ausgeführt werden, aber sie funktionieren nur in den Teams, deren Mitglieder Sie sind oder deren Mitglied Sie sind. Wenn Sie ein globaler Administrator oder Teamdienstadministrator sind, können Sie für alle Teams in Ihrer Organisation agieren.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Die **groupId,** die in den Microsoft Teams PowerShell-Modul-Cmdlets verwendet wird, ist identisch mit der **Identity-Eigenschaft,** die von im Exchange ``Get-UnifiedGroup`` PowerShell-Modul zurückgegeben wird.

## <a name="manage-policies-via-powershell"></a>Verwalten von Richtlinien über PowerShell

> [!NOTE]
> - Skype for Business Online Connector wird in Teams PowerShell konsolidiert. Sie ist derzeit in der öffentlichen Vorschau verfügbar. Mit der Zeit sind Skype for Business Online-Cmdlets, die für Teams gelten, nativ im Teams PowerShell-Modul verfügbar. Installationsschritte sind im [Artikel Installieren von Teams PowerShell](teams-powershell-install.md) verfügbar.
>
> - Die Cmdlets sind in Ihrer PowerShell-Sitzung verfügbar, sobald Sie eine Verbindung mit Skype for Business Online hergestellt haben. Weitere Informationen finden Sie unter Verwalten von [Skype for Business Online mit Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Suchen Sie die Cmdlets zum Verwalten von Richtlinien im [Skype for Business-Cmdletmodul.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

Eine Richtlinie ist eine Gruppe von Einstellungen, die auf einzelne Benutzer präzise angewendet werden können. Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Erstellen, Anzeigen, Löschen und Aktualisieren der Richtlinien selbst und zum Zuweisen dieser Richtlinien zu Benutzern. Die allgemeine Struktur ist:

- **GET-Befehle** (z. B. ): Gibt die Richtliniendokumente zurück, die Sie in Ihrer Organisation zuweisen können, einschließlich der von Microsoft für Sie erstellten Richtlinien sowie der von Ihnen erstellten benutzerdefinierten ``Get-CsTeamsMeetingPolicy`` Richtlinien.
   - Wenn Sie nur die benutzerdefinierten Richtlinien suchen möchten, die Sie in Ihrer Organisation erstellt haben, verwenden Sie ``-Filter "tag:*"`` .

- **NEUE** Befehle (z. B. ``New-CsTeamsMeetingPolicy`` ): Erstellt neue Richtlinien für Ihre Organisation, die Benutzern in Ihrer Organisation zugewiesen werden sollen. Nicht alle Richtlinien unterstützen die Erstellung benutzerdefinierter Richtlinien. Häufig besteht dies daran, sicherzustellen, dass die Richtlinien, die Sie in Ihrer Organisation verwenden, über eine unterstützte Kombination von Einstellungen verfügen.

- **SET-Befehle** (z. B. ``Set-CsTeamsMeetingPolicy`` ): Legt bestimmte Werte für eine bestimmte Richtlinie fest. Für einige Richtlinien sind keine SET-Befehle verfügbar, oder sie enthalten Parameter, die in der Richtlinie nicht angepasst werden können. In den PowerShell-Beschreibungen wird angegeben, welche Parameter nicht angepasst werden können. 
   - Führen Sie aus, um die Richtlinie zu bearbeiten, die standardmäßig Benutzern in Ihrer Organisation zugewiesen wird, denen keine benutzerdefinierte Richtlinie zugewiesen ``Set-Cs<PolicyName> -Identity Global`` ist.

- **REMOVE-Befehle** (z. B. ``Remove-CsTeamsMeetingPolicy`` ): Löscht eine benutzerdefinierte Richtlinie, die in Ihrem Mandanten erstellt wurde. Wenn Sie eine benutzerdefinierte Richtlinie löschen, die mindestens einem Benutzer in Ihrer Organisation zugewiesen wurde, wird dieser Benutzer auf die globale Richtlinie zurückfallen.
   - Sie können die globale Richtlinie in Ihrer Organisation nicht entfernen, aber wenn Sie die globale Richtlinie in Ihrer Organisation auf die von Microsoft bereitgestellten Standardeinstellungen zurücksetzen möchten, führen Sie ``Remove-Cs<PolicyName> -Identity Global`` aus.

- **Befehl GRANT** (z. B. ``Grant-CsTeamsMeetingPolicy`` ): Weist einem bestimmten Benutzer eine Richtlinie zu.
   - Führen Sie aus, um eine benutzerdefinierte Richtlinienzuordnung zu entfernen und den Benutzer auf die Standardrichtlinie in Ihrer Organisation zurückfallen zu ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` lassen.

> [!TIP]
> Nicht alle Richtlinien ermöglichen das Erstellen benutzerdefinierter Richtlinien, und einige Richtlinien verfügen über Einstellungen, die Sie nicht anpassen können (daher können Sie die Einstellung anzeigen, aber während und keinen benutzerdefinierten Wert ``set-`` ``new-`` festlegen). In der Dokumentation für jedes Cmdlet wird angegeben, ob Parameter für die Verwendung durch Kunden verfügbar sind.

Allgemeine Parameter:

- **Identität:** Für , , und bezieht sich der ``Get-`` Parameter Identität immer auf eine bestimmte ``Set-`` ``New-`` ``Remove-`` Richtlinieninstanz.  Für ``Grant`` bezieht sich der Parameter **Identität** auf ein bestimmtes Benutzerobjekt, auf das die Richtlinie angewendet wird.

## <a name="manage-configurations-via-powershell"></a>Verwalten von Konfigurationen über PowerShell

Suchen Sie die Cmdlets zum Verwalten Ihrer Konfiguration im [Skype for Business-Cmdletmodul.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

Konfigurationen sind Buckets mit Einstellungen, die im Dienst verwaltet werden und nicht auf Benutzerebene angegeben werden können. Einstellungen gelten immer für die gesamte Organisation. Ihre globale Konfiguration ist die einzige effektive Konfiguration in Ihrer Organisation. Jeder Konfigurationstyp enthält zwei primäre Cmdlets:

- ``Get-Cs<ConfigurationName>`` (z. B. ``Get-CsTeamsClientConfiguration`` ):

- SET-Befehle (z. B. ``Set-CsTeamsClientConfiguration`` ): Legen Sie Eigenschaften in der Konfiguration dieses Typs fest. Geben Sie die Parameter an, die Sie ändern möchten.
   > Sie können auf die zu ändernde Konfiguration auf eine von zwei Arten verweisen: durch Angeben von -**Identity Global** oder durch Ausführen ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` von .

## <a name="what-can-each-admin-role-do"></a>Was kann jede Administratorrolle tun?

Lesen [Sie Verwenden von Microsoft Teams-Administratorrollen zum](using-admin-roles.md) Verwalten von Teams, um zu verstehen, welche Administratorrollen jedes PowerShell-Cmdlet ausführen können.

## <a name="related-topics"></a>Verwandte Themen

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Versionshinweise zu Teams PowerShell](teams-powershell-release-notes.md)

[Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdletreferenz](/powershell/skype/intro?view=skype-ps)

[Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md)