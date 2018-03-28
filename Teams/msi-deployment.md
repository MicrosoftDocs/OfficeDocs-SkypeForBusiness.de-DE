---
title: Installieren Sie die MSI-Datei von Microsoft-Teams
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Administratoren können die Teams MSI-Datei zu Massen Bereitstellen von Microsoft-Teams, um Benutzer oder Computer auszuwählen.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a>Installieren Sie die MSI-Datei von Microsoft-Teams
===========================================

Um die Nutzung von System Center Configuration Manager oder Gruppenrichtlinien oder 3. Partei Verteilungsmechanismen für umfassenden Bereitstellung hat Microsoft MSI-Dateien ( [32-Bit-](http://aka.ms/teams32bitmsi) und [64-Bit](http://aka.ms/teams64bitmsi)) für Administratoren, die während der Bereitstellung von Massen nutzen bereitgestellt. Microsoft-Teams, Benutzer oder Computer auswählen. Diese Dateien können Administratoren Remotebereitstellung Teams, damit Benutzer keine die app Teams manuell herunterladen. Bei der Bereitstellung automatisch Teams werden Einführung für alle Benutzer, die auf diesem Computer anmelden. Es wird empfohlen, dass Sie das Paket mit dem Computer bereitzustellen, sodass alle neuen Benutzer mit den Computern auch von dieser Bereitstellung profitieren. 
 
> [!Note] 
> Weitere Informationen zu SCCM finden Sie unter. [Einführung zu System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a>Bereitstellungsverfahren (Empfehlungen)
1. Rufen Sie das neueste-Paket
2. Verwenden Sie die Standardwerte vorausgefüllt, durch die MSI-Datei
3. Bereitstellen Sie auf Computern, wenn möglich

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funktionsweise von Microsoft-Teams MSI-Paket

Die Teams MSI-Datei wird Program Files ein Installationsprogramm versehen. Wenn ein Benutzer ein neues Windows-Benutzerprofil anmeldet, das Installationsprogramm wird gestartet, und eine Kopie des Teams Anwendung im Anwendungsdaten-Ordner des Benutzers installiert werden. Wenn ein Benutzer bereits die Teams app im Ordner Anwendungsdaten installiert hat, wird der MSI-Installer den Prozess für diesen Benutzer übersprungen.

Nutzen Sie die MSI-Datei zum Bereitstellen von Updates nicht, der Client automatisch aktualisieren, wenn es erkennt, dass eine neue Version aus dem Dienst verfügbar ist. Verwenden Sie erneut bereitstellen, um der neueste Version von Installer den Prozess der erneutes Bereitstellen von MSI-Datei weiter unten beschriebenen. Wenn Sie eine ältere Version von MSI-Paket bereitstellen, den Client wird automatisch nach Möglichkeit für den Benutzer aktualisieren. Wenn eine sehr alte Version bereitgestellt, ruft ab, wird die MSI-Datei eine Anwendung Aktualisierung auszulösen, bevor der Benutzer Teams nutzen kann. 

> [!Important] 
> Es wird nicht empfohlen, dass Sie alle Installationsverzeichnisse ändern, wie dies den Update-Ablauf unterbrechen könnten. Klicken Sie dann wird dem Benutzer Zugriff auf den Dienst schließlich blockieren. 


## <a name="target-machine-requirements"></a>Anforderungen an die Ziel-Computer:

1. .NET Framework 4.5 oder höher
2. Windows 7 oder höher
2. 32GB Speicherplatz für jedes Benutzerprofil (empfohlen)

## <a name="clean-upredeployment-procedure"></a>Bereinigen Up\redeployment Verfahren
Wenn ein Benutzer von Teams für ihre Benutzerprofil deinstalliert wird, wird der MSI-Installer nachverfolgen, dass der Benutzer hat die app Teams deinstalliert und Teams nicht mehr für dieses Benutzerprofil zu installieren. Wenn Sie Teams erneut bereitstellen für diesen Benutzer auf einem bestimmten Computer, bei denen es war, Sie deinstalliert müssen:

1. Deinstallieren von Teams App für jede Benutzerprofil installiert 
2. Nach dem Deinstallieren, Directory rekursiv unter %localappdata%\Microsoft\Teams\ löschen 
3. Erneutes Bereitstellen des MSI-Pakets an den jeweiligen Computer

> [!TIP] 
> Sie können die [Bereitstellung von Microsoft-Teams, bereinigen Sie](.\scripts\Powershell-script-teams-deployment-clean-up.md) Skript zum Ausführen dieser Schritte 1 und 2 über SCCM nutzen.                                

