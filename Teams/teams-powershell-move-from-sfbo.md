---
title: Wechseln von Skype for Business Online Connector zum PowerShell-Modul von Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie von Skype for Business Online Connector zum Teams PowerShell-Modul wechseln, um Teams zu verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469666"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Wechseln von Skype for Business Online Connector zum PowerShell-Modul von Teams

Um von der Verwendung von Skype for Business Online Connector zum Teams PowerShell-Modul zum Verwalten von Teams zu wechseln, müssen Sie Ihre vorhandenen PowerShell-Skripts aktualisieren. In diesem Artikel wird die Vorgehensweise erläutert.

1. Installieren Sie das neueste PowerShell-Modul für Teams. Eine schrittweise Anleitung finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).
2. Deinstallieren Sie Skype for Business Online Connector. Klicken Sie dazu in der Systemsteuerung auf **Programme und Funktionen**, wählen Sie **Skype for Business Online, Windows PowerShell-Modul**aus, und wählen Sie dann **deinstallieren**aus. 
3. Ändern Sie in ihren PowerShell-Skripts den Modulnamen, auf den in ```Import-Module``` from ```SkypeOnlineConnector``` oder to verwiesen wird ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Ändern Sie beispielsweise ```Import-Module -Name SkypeOnlineConnector``` in ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Administratoren sollten die Verwendung von [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) weiterhin verwenden und die Sitzung importieren, bevor Sie die Skype for Business Online-Cmdlets verwenden. 

## <a name="related-topics"></a>Verwandte Themen

[Installieren von Microsoft Teams PowerShell](teams-powershell-install.md)

[Verwalten von Teams mit PowerShell von Teams](teams-powershell-managing-teams.md)

[Teams PowerShell-Anmerkungen zu dieser Version](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
