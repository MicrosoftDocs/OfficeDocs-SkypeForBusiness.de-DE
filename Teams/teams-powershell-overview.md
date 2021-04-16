---
title: Übersicht über PowerShell für Microsoft Teams
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Microsoft Teams mithilfe der PowerShell-Steuerelemente verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768354"
---
# <a name="microsoft-teams-powershell-overview"></a>Übersicht über PowerShell für Microsoft Teams

Microsoft Teams PowerShell ist eine Gruppe von Cmdlets zum Verwalten von Teams direkt über die PowerShell-Befehlszeile. In .NET Standard geschrieben, funktioniert Teams PowerShell auf PowerShell 5.1 unter Windows, PowerShell 6.x und höher auf allen Plattformen, einschließlich Azure Cloud Shell.

Bevor Sie mit der Verwendung von PowerShell beginnen können, müssen Sie [es installieren.](teams-powershell-install.md) 

> [!WARNING]
> Es gibt bekannte Probleme mit PowerShell 7 und Teams PowerShell. Wir empfehlen die Verwendung von PowerShell 5.1, bis die Probleme behoben sind.

## <a name="releases"></a>Veröffentlichungen


Teams PowerShell ist im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams) in zwei Versionstypen verfügbar.

- **Allgemeine Verfügbarkeit (GA)**: Produktionsbereite Cmdlets, monatlich aktualisiert.

- **Öffentliche Vorschau:** Früher Zugriff auf Features. Kann häufiger aktualisiert werden als GA.

Ausführliche Informationen zu Denk- und Verbesserungen für beide Versionen finden Sie in den Versionshinweisen zu [Teams PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Verwalten von Teams mit PowerShell

Sie verwenden Teams PowerShell-Module, um Teams vollständig zu verwalten:

- [Microsoft Teams PowerShell-Modul:](https://www.powershellgallery.com/packages/MicrosoftTeams/)Das Microsoft Teams PowerShell-Modul enthält Cmdlets zum Verwalten von Teams, Chats und Kanälen.

> [!NOTE]
> Die öffentliche Version 2.0 oder höher von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) umfasst alle Skype for Business Online Connector-Cmdlets, die ein einzelnes Modul für die Verwaltung von Teams PowerShell bereitstellen.

- [Skype for Business PowerShell Connector:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)Der Skype for Business PowerShell-Connector ist jetzt Teil des Teams PowerShell-Moduls.

Einen vollständigen Leitfaden zum Verwalten von Teams mit diesen Modulen finden Sie unter Verwalten von [Teams mit Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Verwandte Themen

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Versionshinweise zu Teams PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdletreferenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdletreferenz](/powershell/skype/intro?view=skype-ps)

[Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
