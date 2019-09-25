---
title: Installieren des StaffHub PowerShell-Moduls
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Vorabversion des Microsoft StaffHub PowerShell-Moduls installieren und eine Verbindung herstellen.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142034"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

> [!IMPORTANT]
> Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt. StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren. Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist. Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Führen Sie die in diesem Artikel aufgeführten Schritte aus, um die Vorabversion des Microsoft StaffHub PowerShell-Moduls zu installieren und eine Verbindung herzustellen. Sie benötigen diese, um [Ihre StaffHub-Teams in Teams zu verschieben](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>Installieren der Vorabversion des Microsoft StaffHub PowerShell-Moduls

1. Öffnen Sie Windows PowerShell 3,0 oder höher als Administrator. Klicken Sie dazu auf **Start**, geben Sie **Windows PowerShell**ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und wählen Sie dann **als Administrator ausführen**aus.
    > [!NOTE]
    > Informationen zum Abrufen der neuesten Version von Windows PowerShell finden Sie unter [Installieren von Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Führen Sie die folgenden Schritte aus, um die Vorabversion des StaffHub PowerShell-Moduls zu installieren:

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. Möglicherweise wird die folgende Warnmeldung angezeigt:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    Geben `Y`Sie ein, und `Enter`klicken Sie dann auf.
 
4. Beenden Sie Windows PowerShell.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Herstellen einer Verbindung mit dem Microsoft StaffHub PowerShell-Modul

1. Führen Sie Folgendes aus:

    ```
    Connect-StaffHub
    ```

2. Wenn Sie dazu aufgefordert werden, melden Sie sich als globaler Administrator an.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft StaffHub PowerShell-Referenz](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams](move-staffhub-teams-to-shifts-in-teams.md)
