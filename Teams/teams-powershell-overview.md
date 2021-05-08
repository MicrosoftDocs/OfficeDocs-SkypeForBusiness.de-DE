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
description: Erfahren Sie, wie Sie die PowerShell-Steuerelemente zum Verwalten von Microsoft Teams.
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

Microsoft Teams PowerShell ist eine Reihe von Cmdlets zum Verwalten von Teams direkt über die PowerShell-Befehlszeile. Die in .NET Standard geschriebene Teams PowerShell funktioniert auf PowerShell 5.1 unter Windows, PowerShell 6.x und höher auf allen Plattformen, einschließlich Azure Cloud Shell.

Bevor Sie mit der Verwendung von PowerShell beginnen können, müssen Sie es [installieren.](teams-powershell-install.md) 

> [!WARNING]
> Es gibt bekannte Probleme mit PowerShell 7 und Teams PowerShell. Wir empfehlen die Verwendung von PowerShell 5.1, bis die Probleme behoben sind.

## <a name="releases"></a>Veröffentlichungen


Teams PowerShell ist im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams) in zwei Veröffentlichungstypen verfügbar.

- **Allgemeine Verfügbarkeit (GA)**: Produktionsfertige Cmdlets, monatlich aktualisiert.

- **Public Preview:** Frühzeitiger Zugriff auf Features. Kann häufiger aktualisiert werden als GA.

Ausführliche Informationen zu den Ergänzungen und Verbesserungen von Features für beide Versionen finden Sie in den Teams [zu PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Verwalten Teams mit PowerShell

Sie verwenden Teams PowerShell-Module, um ihre Daten vollständig zu Teams:

- [Microsoft Teams PowerShell-Modul:](https://www.powershellgallery.com/packages/MicrosoftTeams/)Das Teams PowerShell-Modul enthält Cmdlets zum Verwalten von Teams, Chats und Kanälen.

> [!NOTE]
> Die [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) Public Release, Version 2.0 oder höher, umfasst alle Skype for Business Online Connector-Cmdlets, die ein einzelnes Modul für die PowerShell Teams verwaltung bereitstellen.

- [Skype for Business PowerShell-Connector:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)Der Skype for Business PowerShell-Verbinder ist jetzt ein Bestandteil Teams PowerShell-Moduls.

Eine vollständige Anleitung zum Verwalten von Teams modulen finden Sie unter Verwalten von Teams [mit Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Verwandte Themen

[Installieren Teams PowerShell](teams-powershell-install.md)

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)

[Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
