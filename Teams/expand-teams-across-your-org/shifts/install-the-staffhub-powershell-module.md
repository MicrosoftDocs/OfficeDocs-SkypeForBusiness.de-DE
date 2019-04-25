---
title: Installieren des StaffHub PowerShell-Moduls
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Installieren und mit dem Microsoft StaffHub PowerShell-Modul verbunden.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245916"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

> [!IMPORTANT]
> Die Übermittlung wirksamer wird 1 Oktober 2019, Microsoft StaffHub zurückgezogen werden. Wir erstellen StaffHub-Funktionen in Microsoft-Teams. Heute, Teams enthält die Schichten app für zeitplanverwaltung und zusätzliche Funktionen, die über einen Zeitraum einführen werden. StaffHub werden nicht für alle Benutzer auf 1 Oktober 2019 mehr. Jeder Benutzer, der versucht, StaffHub öffnen wird eine Meldung mit der Weiterleitung zum Herunterladen von Teams angezeigt. Weitere Informationen finden Sie unter [Microsoft StaffHub zurückgezogen werden](microsoft-staffhub-to-be-retired.md).  

Verwenden Sie die Schritte in diesem Artikel zum Installieren und mit dem Microsoft StaffHub PowerShell-Modul verbunden. Sie benötigen diese StaffHub mithilfe von PowerShell verwalten und Ihre StaffHub Teams, die Microsoft-Teams verschieben.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

1. Laden Sie das [StaffHub PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Öffnen Sie Windows PowerShell 3.0 oder höher als Administrator an. Zu diesem Zweck klicken Sie auf **Start**, geben Sie ein **Windows PowerShell**, mit der rechten Maustaste in **Windows PowerShell**, und wählen Sie dann auf **als Administrator ausführen**.
3. Führen Sie Folgendes aus:

    ```
    $ENV:PSModulePath
    ```

4. Überprüfen Sie den Ordnerpfad in der Ausgabe, und stellen Sie sicher, dass alle Ordner im Pfad auf dem Computer vorhanden sind, bevor Sie mit dem nächsten Schritt fortfahren. Wenn Ordner nicht vorhanden sind, erstellen Sie diese.
5. Führen Sie Folgendes ein, wobei &lt;Pfad&gt; ist der Pfad in der Ausgabe aus Schritt 2. Beispielsweise könnte der Pfad C:\Users\User1\Documents\WindowsPowerShell\Modules aussehen.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Verbinden Sie mit dem Microsoft StaffHub PowerShell-Modul

1. Führen Sie Folgendes aus:

    ```
    Connect-StaffHub
    ```

2. Wenn Sie aufgefordert werden, melden Sie sich als ein globaler Administrator an.

## <a name="related-topics"></a>Verwandte Themen

- [Referenz zu Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Verschieben Ihrer Microsoft StaffHub-Teams in Schichten in Teams](move-staffhub-teams-to-shifts-in-teams.md)
