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
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464665"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

> [!IMPORTANT]
> Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt. StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren. Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist. Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Führen Sie die in diesem Artikel aufgeführten Schritte aus, um das Microsoft StaffHub PowerShell-Modul zu installieren und eine Verbindung herzustellen. Sie benötigen diese, um StaffHub mithilfe von PowerShell zu verwalten und ihre StaffHub-Teams in Microsoft Teams zu verschieben.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installieren des Microsoft StaffHub PowerShell-Moduls

1. Öffnen Sie Windows PowerShell 3,0 oder höher als Administrator. Klicken Sie dazu auf **Start**, geben Sie **Windows PowerShell**ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und wählen Sie dann **als Administrator ausführen**aus.
    > [!NOTE]
    > Informationen zum Abrufen der neuesten Version von Windows PowerShell finden Sie unter [Installieren von Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Führen Sie die folgenden Schritte aus, um die aktuelle stabile Version des StaffHub PowerShell-Moduls zu installieren:

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    Sie können diesen Befehl nur ausführen, wenn Sie die neueste Version installieren müssen, die möglicherweise mehr Instabilitäten als die aktuelle stabile Version aufweist:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > Wenn während der Installation der neuesten Version eine Fehlermeldung mit mehr Instabilitäten angezeigt wird, können Sie Folgendes ausführen:`Install-Module PowershellGet -Force`

3. Möglicherweise wird die folgende Warnmeldung angezeigt:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

Geben `Y` Sie ein `Enter`, und klicken Sie darauf.
 
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
