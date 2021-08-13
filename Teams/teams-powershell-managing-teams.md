---
title: Verwalten Teams mit Microsoft Teams PowerShell
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
description: Erfahren Sie, wie Sie Microsoft Teams mithilfe Teams PowerShell verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d149def604b1a80b4af5ce18871b9842c4279d00db4d42c40f3556f5b35214d6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299015"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Verwalten Teams mit Microsoft Teams PowerShell

In diesem Artikel wird beschrieben, wie Sie Microsoft Teams PowerShell zum Verwalten von Teams und Skype for Business. 

Verwenden Sie diesen Leitfaden in Verbindung mit der [Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps) [Skype for Business Referenz für ein Cmdlet.](/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Erstellen und Verwalten von Teams mit PowerShell

Die Cmdlets zum Erstellen und Verwalten von Teams befinden sich im Microsoft Teams [PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Teams werden von Office 365 unterstützt. Wenn Sie also ein Team erstellen, erstellen Sie eine Gruppe. Es gibt eine Reihe von Cmdlets für den Betrieb des Kernteams und seiner Einstellungen ( , , ), verwalten von Teambenutzern ( , ), sowie ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` Cmdlets ``new-teamchannel`` zum Verwalten der Kanäle des Teams ( , ``remove-teamchannel`` ). Alle diese Cmdlets können als Endbenutzer ausgeführt werden, sie funktionieren aber nur in Teams, die Sie besitzen oder deren Mitglied Sie sind. Wenn Sie ein globaler Administrator oder Teams-Administrator sind, können Sie für alle Teams in Ihrer Organisation handeln.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Die **groupId,** die in den Microsoft Teams PowerShell-Modul-Cmdlets verwendet wird, ist identisch mit der **Identity-Eigenschaft,** die von im Exchange ``Get-UnifiedGroup`` PowerShell-Modul zurückgegeben wird.

## <a name="manage-policies-via-powershell"></a>Verwalten von Richtlinien über PowerShell

> [!NOTE]
> - Skype for Business Online Connector wird in PowerShell Teams konsolidiert. Es ist derzeit in Public Preview verfügbar. Mit der Zeit Skype for Business Online-Cmdlets, die für Teams gelten, systemeigene im PowerShell Teams Modul verfügbar. Installationsschritte finden Sie im Artikel [Teams PowerShell.](teams-powershell-install.md)
>
> - Die Cmdlets sind in Ihrer PowerShell-Sitzung verfügbar, sobald Sie eine Verbindung mit Skype for Business online hergestellt haben. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Suchen Sie die Cmdlets zum Verwalten von Richtlinien im [Skype for Business-Cmdlet-Modul](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

Eine Richtlinie ist eine Gruppe von Einstellungen, die auf einzelne Benutzer präzise angewendet werden kann. Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Erstellen, Anzeigen, Löschen und Aktualisieren der Richtlinien selbst und zum anschließenden Zuweisen dieser Richtlinien zu Benutzern. Die allgemeine Struktur ist:

- **GET-Befehle** (z. B. ): Gibt die Richtliniendokumente zurück, die Sie in Ihrer Organisation zuweisen können, einschließlich der von Microsoft erstellten Richtlinien, die Sie verwenden können, sowie der von Ihnen erstellten benutzerdefinierten ``Get-CsTeamsMeetingPolicy`` Richtlinien.
   - Um nur die benutzerdefinierten Richtlinien zu finden, die Sie in Ihrer Organisation erstellt haben, verwenden Sie ``-Filter "tag:*"`` .

- **NEUE** Befehle (z. B. ): Erstellt neue Richtlinien ``New-CsTeamsMeetingPolicy`` für Ihre Organisation, die Benutzern in Ihrer Organisation zugewiesen werden. Nicht alle Richtlinien unterstützen die Erstellung von benutzerdefinierten Richtlinien. Häufig soll so sichergestellt werden, dass die Richtlinien, die Sie in Ihrer Organisation verwenden, über eine unterstützte Kombination von Einstellungen verfügen.

- **SET-Befehle** (z. ``Set-CsTeamsMeetingPolicy`` B. ): Legt bestimmte Werte für eine bestimmte Richtlinie fest. Für einige Richtlinien sind SET-Befehle nicht verfügbar, oder sie enthalten Parameter, die in der Richtlinie nicht angepasst werden können. In den PowerShell-Beschreibungen wird angegeben, welche Parameter nicht angepasst werden können. 
   - Führen Sie aus, um die Richtlinie zu bearbeiten, die standardmäßig Benutzern in Ihrer Organisation zugewiesen wird, denen keine benutzerdefinierte Richtlinie zugewiesen ``Set-Cs<PolicyName> -Identity Global`` ist.

- **REMOVE-Befehle** (z. B. ): Löscht eine benutzerdefinierte Richtlinie, ``Remove-CsTeamsMeetingPolicy`` die in Ihrem Mandanten erstellt wurde. Wenn Sie eine benutzerdefinierte Richtlinie löschen, die mindestens einem Benutzer in Ihrer Organisation zugewiesen wurde, fällt dieser Benutzer auf die globale Richtlinie zurück.
   - Sie können die globale Richtlinie in Ihrer Organisation nicht entfernen, aber wenn Sie die globale Richtlinie in Ihrer Organisation auf die von Microsoft bereitgestellten Standardeinstellungen zurücksetzen möchten, führen Sie ``Remove-Cs<PolicyName> -Identity Global`` aus.

- **GRANT-Befehl** (z. ``Grant-CsTeamsMeetingPolicy`` B. ): Weist einem bestimmten Benutzer eine Richtlinie zu.
   - Führen Sie aus, um eine benutzerdefinierte Richtlinienzuweisung zu entfernen und dafür zu sorgen, dass der Benutzer zur Standardrichtlinie in Ihrer Organisation zurückfallen ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` kann.

> [!TIP]
> Nicht alle Richtlinien erlauben das Erstellen von benutzerdefinierten Richtlinien, und einige Richtlinien verfügen über Einstellungen, die Sie nicht anpassen können (daher können Sie die Einstellung anzeigen, aber keinen benutzerdefinierten Wert während und ``set-`` ``new-`` festlegen). In der Dokumentation für jedes Cmdlet wird angegeben, ob Parameter zur Verwendung durch Kunden verfügbar sind.

Allgemeine Parameter:

- **Identity:** Für , , und bezieht sich der ``Get-`` ``Set-`` ``New-`` ``Remove-`` **Identity-Parameter** immer auf eine bestimmte Richtlinieninstanz. Für ``Grant`` bezieht sich der Parameter **Identity** auf ein bestimmtes Benutzerobjekt, auf das die Richtlinie angewendet wird.

## <a name="manage-configurations-via-powershell"></a>Verwalten von Konfigurationen über PowerShell

Suchen Sie die Cmdlets zum Verwalten Ihrer Konfiguration im [Skype for Business-Cmdlet-Modul .](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

Konfigurationen sind im Dienst verwaltete Einstellungen buckets, die nicht auf Benutzerebene angegeben werden können. Einstellungen gelten immer für die gesamte Organisation. Ihre globale Konfiguration ist die einzige effektive Konfiguration in Ihrer Organisation. Jeder Konfigurationstyp enthält zwei primäre Cmdlets:

- ``Get-Cs<ConfigurationName>`` (z. B. ``Get-CsTeamsClientConfiguration`` ):

- SET-Befehle (z. ``Set-CsTeamsClientConfiguration`` B. ): Legen Sie Eigenschaften in der Konfiguration dieses Typs fest. Geben Sie die Parameter an, die Sie ändern möchten.
   > Sie können auf die zu ändernde Konfiguration auf eine von zwei Arten verweisen: durch Angeben von -**Identity Global** oder durch Ausführen ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` von .

## <a name="what-can-each-admin-role-do"></a>Welche Funktion hat die einzelnen Administratorrolle?

Lesen [Sie Microsoft Teams zum](using-admin-roles.md) Verwalten von Teams, um zu verstehen, welche Administratorrollen die einzelnen PowerShell-Cmdlets ausführen können.

## <a name="related-topics"></a>Verwandte Themen

[Installieren Teams PowerShell](teams-powershell-install.md)

[Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md)

[Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)

[Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md)