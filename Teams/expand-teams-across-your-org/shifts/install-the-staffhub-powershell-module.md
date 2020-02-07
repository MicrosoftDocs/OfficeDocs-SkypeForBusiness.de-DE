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
description: Hier erfahren Sie, wie Sie das Microsoft StaffHub PowerShell-Modul installieren und eine Verbindung herstellen.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75ed6840b409f391b87759e2004c0f1ea475ce69
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827563"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

> [!IMPORTANT]
> 2019, 31. Dezember, wird Microsoft StaffHub eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt. StaffHub wird am 31. Dezember 2019 nicht mehr für alle Benutzer funktionieren. Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist. Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Führen Sie die in diesem Artikel aufgeführten Schritte aus, um das Microsoft StaffHub PowerShell-Modul zu installieren und eine Verbindung herzustellen. Sie benötigen diese, um [Ihre StaffHub-Teams in Teams zu verschieben](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

1. Laden Sie das [StaffHub PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftStaffHub)herunter.
2. Öffnen Sie Windows PowerShell 3,0 oder höher als Administrator. Klicken Sie dazu auf **Start**, geben Sie **Windows PowerShell**ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und wählen Sie dann **als Administrator ausführen**aus.
    > [!NOTE]
    > Informationen zum Abrufen der neuesten Version von Windows PowerShell finden Sie unter [Installieren von Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).
3. Führen Sie Folgendes aus:

    ```PowerShell
    $ENV:PSModulePath
    ```
4. Überprüfen Sie den Ordnerpfad in der Ausgabe, und stellen Sie sicher, dass alle Ordner im Pfad auf dem Computer vorhanden sind, bevor Sie mit dem nächsten Schritt fortfahren. Wenn Ordner fehlen, erstellen Sie Sie.
5. Führen Sie die folgenden Schritte aus, um die Installation des StaffHub PowerShell-Moduls zu ermöglichen:

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. Führen Sie die folgenden Schritte &lt;aus&gt; , wobei Path der Pfad in der Ausgabe aus Schritt 3 ist. Der Pfad sieht beispielsweise wie C:\Users\User1\Documents\WindowsPowerShell\Modules. aus.

    Stellen Sie sicher, dass Sie jeden Befehl separat ausführen.

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Beenden Sie Windows PowerShell.
8. Öffnen Sie Windows PowerShell 3,0 oder höher als globaler Administrator, und führen Sie dann die folgenden Aktionen aus:

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Herstellen einer Verbindung mit dem Microsoft StaffHub PowerShell-Modul

1. Führen Sie Folgendes aus:

    ```PowerShell
    Connect-StaffHub
    ```

2. Wenn Sie dazu aufgefordert werden, melden Sie sich als globaler Administrator an.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft StaffHub PowerShell-Referenz](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams](move-staffhub-teams-to-shifts-in-teams.md)
