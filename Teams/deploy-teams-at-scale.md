---
title: Bereitstellen von Teams im großen Maßstab für Mitarbeiter in Service und Produktion in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Teams im großen Maßstab für die Mitarbeiter in Service und Produktion in Ihrer Organisation bereitstellen.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947228"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Bereitstellen von Teams im großen Maßstab für Mitarbeiter in Service und Produktion in Microsoft Teams

> [!NOTE]
> Dieses Feature befindet sich derzeit in der privaten Vorschau. Wenn Sie an der privaten Vorschau teilnehmen möchten, wenden Sie sich an uns unter [dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Übersicht
 
Ihre Organisation verfügt möglicherweise über viele Teams, die Sie verwenden, um die Kommunikation und Zusammenarbeit zwischen Ihren Mitarbeitern in Service und Produktion zu fördern, die über verschiedene Geschäfte, Standorte und Rollen verteilt sind. Derzeit gibt es keine einfache Lösung zum Bereitstellen, Einrichten und Verwalten dieser Teams und Benutzer im großen Maßstab.

Wir erstellen eine Lösung, mit der Administratoren Teams im großen Maßstab bereitstellen und verwalten können.

Hier ist eine Übersicht über die Funktionen, die heute verfügbar sind, um eine große Anzahl von Teams gleichzeitig zu erstellen und zu verwalten, und was wir für die nahe Zukunft planen.

||Heute verfügbar |Später im Jahr 2022  |
|---------|---------|---------|
|**Anzahl der Teams, die Sie pro Batch erstellen können**|Bis zu 100 |Bis zu 500|
|**Anzahl der Benutzer, die Sie pro Team hinzufügen können**|Bis zu 25|Bis zu 25|

Die Bereitstellung von Teams im großen Maßstab ermöglicht Folgendes:

- Erstellen Sie Teams mithilfe vordefinierter Vorlagen oder ihrer eigenen benutzerdefinierten Vorlagen.
- Hinzufügen von Benutzern zu Teams als Besitzer oder Mitglieder.
- Verwalten Sie Teams im großen Maßstab, indem Sie Benutzer zu vorhandenen Teams hinzufügen oder daraus entfernen.
- Bleiben Sie per E-Mail benachrichtigt, einschließlich Abschluss, Status und Fehler (falls vorhanden). Teambesitzer und -mitglieder werden benachrichtigt.

## <a name="how-to-deploy-teams-at-scale"></a>So stellen Sie Teams im großen Maßstab bereit

> [!NOTE]
> Stellen Sie vor der Bereitstellung Ihrer Teams sicher, dass alle Teambesitzer über eine Teams-Lizenz verfügen.

Führen Sie die folgenden Schritte aus, um eine große Anzahl von Teams gleichzeitig bereitzustellen.

Sie verwenden das ```New-CsBatchTeamsDeployment``` Cmdlet, um eine Reihe von Teams zum Erstellen zu übermitteln. Für jeden Batch wird eine Orchestrierungs-ID generiert. Anschließend können Sie das ```Get-CsBatchTeamsDeployment``` Cmdlet verwenden, um den Fortschritt und Status jedes Batches nachzuverfolgen.

1. Installieren Sie PowerShell, Version 7 oder höher. Eine schrittweise Anleitung finden Sie unter [Installieren von PowerShell unter Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Führen Sie PowerShell im Administratormodus aus.
1. Führen Sie die folgenden Schritte aus, um alle zuvor installierten Teams PowerShell-Module zu deinstallieren.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Wenn eine Fehlermeldung angezeigt wird, sind Sie bereits festgelegt. Fahren Sie mit dem nächsten Schritt fort.
1. Laden Sie die [neueste Version des Teams PowerShell-Moduls](https://www.powershellgallery.com/packages/MicrosoftTeams) herunter, und installieren Sie sie.

1. Führen Sie Folgendes aus, um eine Verbindung mit Teams herzustellen.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

1. Führen Sie die folgenden Schritte aus, um eine Liste der Befehle im Teams PowerShell-Modul abzurufen.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Vergewissern Sie sich, dass ```New-CsBatchTeamsDeployment``` und ```Get-CsBatchTeamsDeployment``` aufgeführt sind.

1. Führen Sie die folgenden Schritte aus, um eine Reihe von Teams bereitzustellen. Sie können bis zu fünf E-Mail-Adressen in den Parameter **"UsersToNotify** " eingeben.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. Führen Sie die folgenden Schritte aus, um den Status des von Ihnen übermittelten Batches zu überprüfen.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Senden Sie uns Feedback.

Wir schätzen Ihr Feedback. Nutzbarkeit, Zuverlässigkeit, Leistung&mdash;wir freuen uns über alles!

[E-Mail-dscale@microsoft.com](mailto:dscale@microsoft.com) und fügen Sie Ihre Orchestrierungs-ID und Fehlerdatei ein, sofern vorhanden.

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
