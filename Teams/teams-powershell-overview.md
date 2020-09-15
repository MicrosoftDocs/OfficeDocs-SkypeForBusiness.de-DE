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
description: Erfahren Sie, wie Sie die PowerShell-Steuerelemente zum Verwalten von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5986a730ed678d45360d89efbd35693134c2a6a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814364"
---
# <a name="microsoft-teams-powershell-overview"></a>Übersicht über PowerShell für Microsoft Teams

Microsoft Teams PowerShell ist eine Gruppe von Cmdlets zum direkten Verwalten von Teams über die PowerShell-Befehlszeile. Das in .NET Standard geschriebene Teams PowerShell funktioniert auf allen Plattformen, einschließlich Azure Shell, auf PowerShell 5,1 unter Windows, PowerShell 6. x und höher.

Bevor Sie mit der Verwendung von PowerShell beginnen können, müssen Sie Sie [Installieren](teams-powershell-install.md). 

> [!WARNING]
> Es gibt bekannte Probleme mit PowerShell 7 und PowerShell von Teams. Es wird empfohlen, PowerShell 5,1 zu verwenden, bis die Probleme behoben wurden.

## <a name="releases"></a>Mitteilungen


Teams PowerShell steht im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams) in zwei Veröffentlichungstypen zur Verfügung.

- **Allgemeine Verfügbarkeit (GA)**: produktionsfähige Cmdlets, monatlich aktualisiert.

- **Öffentliche Vorschau**: früher Zugriff auf Funktionen. Kann häufiger als GA aktualisiert werden.

Detaillierte Informationen zu den Funktionserweiterungen und Verbesserungen für beide Versionen finden Sie in den Versionshinweisen zu [Teams PowerShell](teams-powershell-release-notes.md).


## <a name="manage-teams-with-powershell"></a>Verwalten von Teams mit PowerShell

Sie verwenden Teams PowerShell-Module, um Teams vollständig zu verwalten:

- [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/): Das PowerShell-Modul von Teams enthält Cmdlets für die Verwaltung von Teams, Chats und Kanälen.

> [!NOTE]
> Die neueste [PowerShell-Version von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und bietet ein einzelnes Modul für die PowerShell-Verwaltung von Teams.

- [Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): der Skype for Business PowerShell-Connector ist nun Teil des Teams PowerShell-Moduls.

Eine vollständige Anleitung zum Verwalten von Teams, die diese Module verwenden, finden Sie unter Verwalten von Teams [mit PowerShell für Teams](teams-powershell-managing-teams.md).


## <a name="related-topics"></a>Verwandte Themen

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit PowerShell von Teams](teams-powershell-managing-teams.md)

[Teams PowerShell-Anmerkungen zu dieser Version](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
