---
title: Teams PowerShell (Übersicht)
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: article
ms.service: msteams
description: Erfahren Sie, die PowerShell-Steuerelemente verwenden Sie zum Verwalten von Microsoft-Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 181655609fd031da177a21e10684186ca5c52066
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294720"
---
# <a name="teams-powershell-overview"></a>Teams PowerShell (Übersicht)

Microsoft-Teams, verfügt über einen umfassenden Satz von Tools für IT-Administratoren zur Verwaltung des Produkts über das Microsoft-Teams & Skype für Business Admin Center, PowerShell Steuerelemente und Diagramm-APIs. In diesem Handbuch wird erläutert, wie wir unsere PowerShell-Cmdlets für IT-Administratoren verwenden, strukturieren und enthält Verweise auf Weitere Dokumentation. Beachten Sie, dass unterschiedliche Teams Administratorrollen auf anderen Cmdlets zugreifen. Weitere Informationen finden Sie unter [Verwendung von Microsoft-Teams Administratorrollen zum Verwalten von Teams](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Welche Module müssen Sie verwenden?

Für die Verwaltung von Microsoft-Teams, die PowerShell-Steuerelemente befinden sich in zwei verschiedene PowerShell-Module: [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3) (public Preview) und die [Skype für Business PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Das Teams PowerShell-Modul enthält alle Cmdlets, die Sie zum Erstellen und Verwalten von Teams benötigen, während die Skype für Business PowerShell-Modul die Steuerelemente für die Verwaltung von Richtlinien, Konfigurationen und andere Tools von Teams enthält. Die Referenzdokumente für PowerShell Steuerelemente erfahren Sie, welche Modul mit dem Cmdlet enthält, das Sie untersuchen möchten. (Schließlich werden die zwei Module kombiniert werden.)

## <a name="what-can-each-admin-role-do"></a>Welche Vorteile jedes Administratorrolle?

Lesen Sie [Administratorrollen verwalten Teams verwenden Microsoft-Teams,](using-admin-roles.md) um zu verstehen, welche Administratorrollen von PowerShell-Cmdlets verschiedene nutzen können.

## <a name="creating-and-managing-teams-via-powershell"></a>Erstellen und Verwalten von Teams über die PowerShell

Die Cmdlets für das Erstellen und Verwalten von Teams sind im [Microsoft-Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3). 

Teams sind gesichert nach Office 365-Gruppen, also wenn Sie ein Team erstellen, erstellen Sie eine Gruppe. Es gibt eine Gruppe von Cmdlets für den Betrieb auf das Team Core und die zugehörigen Einstellungen bereitgestellt (``new-team``, ``get-team``, ``set-teamfunsettings``), sowie von Cmdlets für die Verwaltung der Kanäle des Teams (``new-teamchannel``, ``remove-teamchannel``). Alle diese Cmdlets als Endbenutzer ausgeführt werden können, aber sie nur auf den Teams, die Sie besitzen oder ein Mitglied arbeiten. Wenn Sie ein globaler Administrator oder Teams Service-Administrator sind, werden Sie auf alle Teams in Ihrer Organisation agieren sein.

> Die in den Microsoft-Teams PowerShell-Modul-Cmdlets verwendet **GroupId** ist identisch mit der **Identity** -Eigenschaft zurückgegebene ``Get-UnifiedGroup`` in der Exchange PowerShell-Modul.

## <a name="managing-policies-via-powershell"></a>Verwalten von Richtlinien über die PowerShell

Die Cmdlets zum Verwalten von Richtlinien sind in der [Skype für Business-Cmdlet Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Eine Richtlinie ist eine Gruppe von Einstellungen, die detaillierte auf einzelne Benutzer angewendet werden kann. Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Erstellen, anzeigen, löschen, und aktualisieren die Richtlinien selbst und dann diese Richtlinien Benutzern zuweisen. Die allgemeine Struktur ist:

- GET-Befehle (z. B. ``Get-CsTeamsMeetingPolicy``): die Richtlinie Dokumente, die in Ihrer Organisation, die Richtlinien von Microsoft für die Verwendung erstellt und die benutzerdefinierten Richtlinien, die Sie erstellt haben Zuweisung von verfügbar sind.
   > Wenn Sie nur die benutzerdefinierten Richtlinien finden Sie in Ihrer Organisation erstellt haben möchten, können Sie ``-Filter "tag:*"``.

- NEUE Befehle (z. B. ``New-CsTeamsMeetingPolicy``): können Sie die neue Richtlinien für Ihre Organisation zu erstellen, klicken Sie dann auf die Benutzern in Ihrer Organisation zugewiesen werden verfügbar sind. Nicht alle Richtlinien unterstützen die Erstellung von benutzerdefinierten Richtlinien. Häufig ist dies stellen Sie sicher, dass die Richtlinien für die Verwendung in Ihrer Organisation eine unterstützte Kombination von Einstellungen haben.

- SET-Befehle (z. B. ``Set-CsTeamsMeetingPolicy``): ermöglicht das Festlegen bestimmter Werte für eine bestimmte Richtlinie. Einige Richtlinien haben Set-Befehle zur Verfügung, oder nicht enthalten Parameter, die in der Richtlinie nicht angepasst werden können. Jede PowerShell Beschreibung wird aufgerufen, welche Parameter können nicht angepasst werden. 
   > Um die Richtlinie zu bearbeiten, das standardmäßig an Benutzer in Ihrer Organisation zugewiesen wird, die nicht über eine benutzerdefinierte Richtlinie zugewiesen verfügen, führen Sie ``Set-Cs<PolicyName> -Identity Global``.

- Entfernen Sie Befehle (z. B. ``Remove-CsTeamsMeetingPolicy``): Sie können dieses Cmdlet verwenden, um eine benutzerdefinierte Richtlinie zu löschen, die in Ihrem Mandanten erstellt wurde. Wenn Sie eine benutzerdefinierte Richtlinie, die mindestens ein Benutzer in Ihrer Organisation zugewiesen wurde löschen, wird der Benutzer auf die globale Richtlinie zurückgreifen.
   > Sie können die globale Richtlinie nicht tatsächlich in Ihrer Organisation entfernen, aber wenn Sie die globale Richtlinie in Ihrer Organisation und die Microsoft bereitgestellten Standardeinstellungen zurücksetzen möchten, können Sie ausführen ``Remove-Cs<PolicyName> -Identity Global``.

- GRANT-Befehl (z. B. ``Grant-CsTeamsMeetingPolicy``): ermöglicht das Zuweisen einer Richtlinie für einen bestimmten Benutzer.
   > Um eine benutzerdefinierte Richtlinie Zuordnung zu entfernen, und stellen Sie den Benutzer auf die Standardrichtlinie in Ihrer Organisation zurückgreifen, führen Sie ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> Nicht alle Richtlinien zulassen benutzerdefinierte Richtlinien erstellt werden soll, und einige Richtlinien aufweisen, die Sie anpassen können keine Einstellungen (so zeigen Sie die Einstellung kann jedoch einen benutzerdefinierten Wert kann nicht festgelegt werden ``set-`` und ``new-``). Die Dokumentation des entsprechenden Cmdlet wird Legende, wenn der Parameter nicht für die Verwendung durch den Kunden verfügbar sind.

Allgemeine Parameter:

- **Identität**: für ``Get-``, ``Set-``, ``New-``, und ``Remove-``, verweist der Parameter **Identity** immer auf eine bestimmte Richtlinie-Instanz. Für ``Grant``, der **Identity** -Parameter verweist auf ein bestimmtes Benutzerobjekt, denen die Richtlinie angewendet wird.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Verwalten von Konfigurationen über die PowerShell

Die Cmdlets für die Verwaltung Ihrer Konfigurations sind in der [Skype für Business-Cmdlet Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Konfigurationen werden Buckets Einstellungen verwaltet, in der Dienst, der auf der Benutzerebene nicht angegeben werden kann. Die Einstellungen werden immer in der gesamten Organisation gelten. Die globale Konfiguration ist die einzige effektive Konfiguration in Ihrer Organisation. Jedes Configuration-Typ verfügt über zwei primäre Cmdlets:

- ``Get-Cs<ConfigurationName>``(z. B. ``Get-CsTeamsClientConfiguration``): 

- SET-Befehle (z. B. ``Set-CsTeamsClientConfiguration``): Festlegen der Eigenschaften in die Konfiguration dieses Typs. Geben Sie die Parameter, die Sie ändern möchten.
   > Sie können die Konfiguration, die Sie in einem der folgenden beiden Methoden ändern, sind verweisen: durch Angabe -**Identity Global**, oder durch Ausführen von ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Andere Tools von PowerShell

Finden Sie ausführliche Anweisungen zum alle PowerShell-Steuerelemente verwenden Sie zum Verwalten von Microsoft-Teams und Skype für Unternehmen, einschließlich detaillierte Beschreibung der Einstellungen in den einzelnen Richtlinien, in der [Microsoft-Teams, Cmdlet-Referenz](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps) und [Skype für Referenz zu den Business](https://docs.microsoft.com/en-us/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Weitere Informationen

- [Cmdlet-Referenz zu Microsoft-Teams](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)
- [Skype für Business-Cmdlet-Referenz](https://docs.microsoft.com/en-us/powershell/skype/intro?view=skype-ps)
- [Verwenden von Microsoft-Teams, Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
