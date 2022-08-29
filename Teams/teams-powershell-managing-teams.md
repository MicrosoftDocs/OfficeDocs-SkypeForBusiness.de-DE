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
description: Erfahren Sie, wie Sie Microsoft Teams mithilfe von Teams PowerShell verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66f873b163222d3d9745e68881da2b8071f60eec
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396526"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Verwalten von Teams mit Microsoft Teams PowerShell

In diesem Artikel erfahren Sie, wie Sie Microsoft Teams PowerShell zum Verwalten von Teams und Skype for Business verwenden.

Verwenden Sie diese Anleitung in Verbindung mit der [Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps) und [Skype for Business Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps).

Informationen zum Verwalten von Teams im Teams Admin Center finden [Sie unter Verwalten von Teams mit Azure Cloud Shell](#manage-teams-with-azure-cloud-shell).

## <a name="create-and-manage-teams-using-powershell"></a>Erstellen und Verwalten von Teams mithilfe von PowerShell

Die Cmdlets zum Erstellen und Verwalten von Teams befinden sich im [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Teams werden von Office 365 Gruppen unterstützt. Wenn Sie also ein Team erstellen, erstellen Sie eine Gruppe. Es gibt eine Reihe von Cmdlets für die Arbeit im Kernteam und dessen Einstellungen (, , ), die Verwaltung von Teambenutzern (``add-teamuser``, ``remove-teamuser``), sowie Cmdlets zum Verwalten der Kanäle des Teams (``new-teamchannel``, ``remove-teamchannel``). ``set-team````get-team````new-team`` Alle diese Cmdlets können als Endbenutzer ausgeführt werden, funktionieren aber nur in den Teams, die Sie besitzen oder mitglied sind. Wenn Sie ein globaler Admin oder Teams-Administrator sind, können Sie auf alle Teams in Ihrer Organisation reagieren.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> Die in den Microsoft Teams PowerShell-Modul-Cmdlets verwendete **GroupId** entspricht der **Identitätseigenschaft** , die im ``Get-UnifiedGroup`` Exchange PowerShell-Modul zurückgegeben wird.

## <a name="manage-teams-with-azure-cloud-shell"></a>Verwalten von Teams mit Azure Cloud Shell

Cloud Shell ist eine interaktive, authentifizierte, browserfreundliche Shell, mit der Sie Ihre Ressourcen verwalten können. Weitere Informationen zu Cloud Shell finden Sie unter [Azure Cloud Shell](/azure/cloud-shell/overview).

Um auf die Azure Cloud Shell zuzugreifen und PowerShell zum Verwalten von Teams zu verwenden, melden Sie sich beim Teams Admin Center an.

1. Wählen Sie das Symbol Cloud Shell in der oberen rechten Ecke aus.

    ![Screenshot des Teams Admin Center-Headers mit Cloud Shell Symbol.](media/cloud-shell-icon-select.png)

1. Wenn Sie dazu aufgefordert werden, wählen Sie **PowerShell** aus.

    ![Screenshot der Azure Cloud Shell-Eingabeaufforderung.](media/cloud-shell.png)

1. Führen Sie den folgenden Befehl aus, um eine Teams PowerShell-Sitzung zu starten:

    ```powershell
    Connect-MicrosoftTeams
    ```

Nachdem Sie diese Schritte abgeschlossen haben, können Sie Teams PowerShell-Befehle ausführen.

> [!IMPORTANT]
> Wenn Sie Cs*-Cmdlets verwenden möchten, müssen Sie zuerst mithilfe des ``Connect-MicrosoftTeams -UseDeviceAuthentication`` Befehls eine Verbindung mit Teams herstellen.

## <a name="manage-policies-via-powershell"></a>Verwalten von Richtlinien über PowerShell

> [!NOTE]
> - Skype for Business Online Connector wird in Teams PowerShell konsolidiert. Es ist derzeit in der öffentlichen Vorschau verfügbar. Rechtzeitig sind Skype for Business Online-Cmdlets, die für Teams gelten, nativ im Teams PowerShell-Modul verfügbar. Die Installationsschritte finden Sie im Artikel ["Installieren von Teams PowerShell](teams-powershell-install.md) ".
> - Die Cmdlets sind in Ihrer PowerShell-Sitzung verfügbar, sobald Sie eine Verbindung mit Skype for Business Online herstellen. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Suchen Sie die Cmdlets zum Verwalten von Richtlinien im [Skype for Business Cmdlet-Modul](/powershell/module/teams).

Eine Richtlinie ist eine Gruppe von Einstellungen, die auf einzelne Benutzer präzise angewendet werden können. Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Erstellen, Anzeigen, Löschen und Aktualisieren der Richtlinien selbst und zum anschließenden Zuweisen dieser Richtlinien zu Benutzern. Die allgemeine Struktur ist:

- **GET-Befehle** (z. B. ): Gibt die Richtliniendokumente zurück, ``Get-CsTeamsMeetingPolicy``die Sie in Ihrer Organisation zuweisen können, einschließlich der von Microsoft für Sie erstellten Richtlinien sowie der von Ihnen erstellten benutzerdefinierten Richtlinien.
  - Um nur die benutzerdefinierten Richtlinien zu finden, die Sie in Ihrer Organisation erstellt haben, verwenden Sie ``-Filter "tag:*"``.

- **NEUE** Befehle (z. B. ``New-CsTeamsMeetingPolicy``): Erstellt neue Richtlinien für Ihre Organisation, die Benutzern in Ihrer Organisation zugewiesen werden sollen. Nicht alle Richtlinien unterstützen die Erstellung benutzerdefinierter Richtlinien. Häufig wird dadurch sichergestellt, dass die Richtlinien, die Sie in Ihrer Organisation verwenden, über eine unterstützte Kombination von Einstellungen verfügen.

- **SET-Befehle** (z. B ``Set-CsTeamsMeetingPolicy``. ): Legt bestimmte Werte für eine bestimmte Richtlinie fest. Für einige Richtlinien sind keine SET-Befehle verfügbar, oder sie enthalten Parameter, die in der Richtlinie nicht angepasst werden können. In den PowerShell-Beschreibungen erfahren Sie, welche Parameter nicht angepasst werden können.
  - Um die Richtlinie zu bearbeiten, die standardmäßig Benutzern in Ihrer Organisation zugewiesen wird, denen keine benutzerdefinierte Richtlinie zugewiesen ist, führen Sie ``Set-Cs<PolicyName> -Identity Global``.

- **REMOVE-Befehle** (z. B ``Remove-CsTeamsMeetingPolicy``. ): Löscht eine benutzerdefinierte Richtlinie, die in Ihrem Mandanten erstellt wurde. Wenn Sie eine benutzerdefinierte Richtlinie löschen, die mindestens einem Benutzer in Ihrer Organisation zugewiesen wurde, fällt dieser Benutzer auf die globale Richtlinie zurück.
  - Sie können die globale Richtlinie in Ihrer Organisation nicht wirklich entfernen, aber wenn Sie die globale Richtlinie in Ihrer Organisation auf die von Microsoft bereitgestellten Standardeinstellungen zurücksetzen möchten, führen Sie diese aus ``Remove-Cs<PolicyName> -Identity Global``.

- **GRANT-Befehl** (z. B ``Grant-CsTeamsMeetingPolicy``. ): Weist einem bestimmten Benutzer eine Richtlinie zu.
  - Führen Sie die Ausführung aus, ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``um eine benutzerdefinierte Richtlinienzuweisung zu entfernen und den Benutzer auf die Standardrichtlinie in Ihrer Organisation zurückgreifen zu lassen.

> [!TIP]
> Nicht alle Richtlinien erlauben das Erstellen benutzerdefinierter Richtlinien, und einige Richtlinien verfügen über Einstellungen, die Sie nicht anpassen können (sodass Sie die Einstellung anzeigen, aber während und ``new-``nicht festlegen ``set-`` können). Die Dokumentation für jedes Cmdlet gibt an, ob Parameter für die Verwendung durch Kunden verfügbar sind.

Allgemeine Parameter:

- **Identity**: For ``Get-``, ``Set-``, , ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance. For ``Grant``bezieht sich der **Parameter Identity** auf ein bestimmtes Benutzerobjekt, auf das die Richtlinie angewendet wird.

## <a name="manage-configurations-via-powershell"></a>Verwalten von Konfigurationen über PowerShell

Suchen Sie die Cmdlets zum Verwalten Ihrer Konfiguration im [Skype for Business-Cmdlet-Modul](/powershell/module/skype).

Konfigurationen sind Buckets von Einstellungen, die im Dienst verwaltet werden und nicht auf Benutzerebene angegeben werden können. Einstellungen gelten immer für die gesamte Organisation. Ihre globale Konfiguration ist die einzige effektive Konfiguration in Ihrer Organisation. Jeder Konfigurationstyp verfügt über zwei primäre Cmdlets:

- ``Get-Cs<ConfigurationName>`` (z. ``Get-CsTeamsClientConfiguration``B.: ):

- SET-Befehle (z. B ``Set-CsTeamsClientConfiguration``. ): Legen Sie Eigenschaften in der Konfiguration dieses Typs fest. Geben Sie die Parameter an, die Sie ändern möchten.
    > [!NOTE]
    > Sie können auf zwei Arten auf die Konfiguration verweisen, die Sie ändern: durch Angeben von -**Identity Global** oder durch Ausführen ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``von .

## <a name="what-can-each-admin-role-do"></a>Was kann jede Administratorrolle tun?

Lesen [Sie "Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md) ", um zu verstehen, welche Administratorrollen jedes PowerShell-Cmdlet ausführen können.

## <a name="related-topics"></a>Verwandte Themen

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Versionshinweise zu Teams PowerShell](teams-powershell-release-notes.md)

[Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)

[Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md)
