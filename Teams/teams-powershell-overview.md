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
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943988"
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

Sie verwenden diese beiden PowerShell-Module zum vollständigen Verwalten von Teams:

- [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams/): Das PowerShell-Modul von Teams enthält Cmdlets für die Verwaltung von Teams, Chats und Kanälen.

- [Skype for Business PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366): das Skype for Business PowerShell-Modul enthält die Cmdlets zum Verwalten von Besprechungen, Telefonsystem und Richtlinienfeatures.

Eine vollständige Anleitung zum Verwalten von Teams, die diese Module verwenden, finden Sie unter Verwalten von Teams [mit PowerShell für Teams](teams-powershell-managing-teams.md).

> [!NOTE]
> Die neueste [Version von Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und bietet ein einzelnes Modul für die PowerShell-Verwaltung von Teams.

## <a name="related-topics"></a>Verwandte Themen

[Installieren von Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit PowerShell von Teams](teams-powershell-managing-teams.md)

[Teams PowerShell-Anmerkungen zu dieser Version](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md)
