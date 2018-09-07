---
title: Installieren Sie die MSI-Datei von Microsoft-Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Administratoren können die Teams MSI-Datei zu Massen Bereitstellen von Microsoft-Teams, um Benutzer oder Computer auszuwählen.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7176b990c41f2792f0955ac3ca2e937632a707d7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854141"
---
<a name="install-microsoft-teams-using-msi"></a>Installieren Sie die MSI-Datei von Microsoft-Teams
=================================

Verwendung von System Center Configuration Manager oder Gruppenrichtlinien oder Drittanbieter-Verteilungsmechanismen für umfassenden Bereitstellung hat Microsoft MSI-Dateien ( [32-Bit-](https://aka.ms/teams32bitmsi) und [64-Bit](https://aka.ms/teams64bitmsi)) bereitgestellt, mit denen Administratoren für die Bereitstellung von Teams Massen können wählen Benutzer oder Computer. Diese Dateien können Administratoren Remotebereitstellung Teams, damit Benutzer keine die app Teams manuell herunterladen. Bei der Bereitstellung automatisch Teams werden Einführung für alle Benutzer, die auf diesem Computer anmelden. Es wird empfohlen, dass Sie das Paket auf dem Computer bereitzustellen, sodass alle neuen Benutzer des Computers auch von dieser Bereitstellung profitieren. 
 
> [!Note] 
> Weitere Informationen zu SCCM finden Sie unter [Einführung zu System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Bereitstellungsverfahren (empfohlen)
1. Rufen Sie das neueste-Paket.
2. Verwenden Sie die Standardeinstellungen, durch die MSI-Datei vorausgefüllt.
3. Bereitstellen Sie auf Computern, wenn möglich.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funktionsweise von Microsoft-Teams MSI-Paket

Die Teams MSI-Datei wird Program Files ein Installationsprogramm versehen. Wenn ein Benutzer ein neues Windows-Benutzerprofil anmeldet, das Installationsprogramm wird gestartet, und eine Kopie der Anwendung Teams im Anwendungsdaten-Ordner des Benutzers installiert werden. Wenn ein Benutzer bereits die Teams app im Ordner Anwendungsdaten installiert hat, wird der MSI-Installer den Prozess für diesen Benutzer übersprungen.

Verwenden Sie die MSI-Datei nicht zum Bereitstellen von Updates, da der Client Update automatisch wird, wenn es erkennt, dass eine neue Version aus dem Dienst verfügbar ist. Verwenden Sie erneut bereitstellen, um der neueste Version von Installer den Prozess der erneutes Bereitstellen von MSI-Datei weiter unten beschriebenen. Wenn Sie eine ältere Version von MSI-Paket bereitstellen, den Client wird automatisch nach Möglichkeit für den Benutzer aktualisieren. Wenn eine sehr alte Version bereitgestellt, ruft ab, wird die MSI-Datei eine Anwendung Aktualisierung auszulösen, bevor der Benutzer Teams nutzen kann. 

> [!Important] 
> Wir empfohlen nicht, die Standardspeicherorte Installation zu ändern, wie dies den Update-Ablauf unterbrechen könnten. Mit einer zu alten Version wird schließlich Benutzer Zugriff auf den Dienst blockieren. 


## <a name="target-computer-requirements"></a>Anforderungen für die Ziel-computer

- .NET Framework 4.5 oder höher
- Windows 7 oder höher
- 3 GB freier Festplattenspeicher für die einzelnen Benutzerprofilen (empfohlen)

## <a name="clean-up-and-redeployment-procedure"></a>Bereinigen und Verfahren für die erneute Bereitstellung
Wenn ein Benutzer aus ihrem Benutzerprofil Teams deinstalliert, wird der MSI-Installer nachverfolgen, dass der Benutzer hat die app Teams deinstalliert und Teams nicht mehr für dieses Benutzerprofil zu installieren. Um Teams für diesen Benutzer auf einem bestimmten Computer erneut bereitstellen, auf dem sie deinstalliert wurde, führen Sie folgende Schritte aus:

1. Deinstallieren von Teams App für jede Benutzerprofil installiert. 
2. Nach dem Deinstallieren, Directory rekursiv unter % localappdata%\Microsoft\Teams\ löschen. 
3. Erneutes Bereitstellen des MSI-Pakets an dem jeweiligen Computer.

> [!TIP] 
> [Bereitstellung von Microsoft-Teams, bereinigen Sie](.\scripts\Powershell-script-teams-deployment-clean-up.md) Skript können Sie die Schritte 1 und 2 über SCCM erreichen.                              

