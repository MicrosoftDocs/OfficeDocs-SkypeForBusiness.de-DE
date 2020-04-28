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
description: Hier erfahren Sie, wie Sie das Microsoft StaffHub PowerShell-Modul installieren und eine Verbindung herstellen und ihre StaffHub-Teams in Microsoft Teams verschieben.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52b4e0c41520468bc1e05734644d1beb05fed5be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905727"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

> [!IMPORTANT]
> Am 31. Dezember 2019 wird Microsoft StaffHub eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub wird am 31. Dezember 2019 für alle Benutzer eingestellt. Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet. Weitere Informationen finden Sie unter [Microsoft StaffHub wird eingestellt](microsoft-staffhub-to-be-retired.md).  

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
