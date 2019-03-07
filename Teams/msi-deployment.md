---
title: Installieren von Microsoft Teams mithilfe eines MSI-Pakets (mit SCCM)
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Administratoren können das Microsoft Teams-MSI-Paket für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5ffceef19e91f5d3e694db7655d23efb67498ae
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464348"
---
<a name="install-microsoft-teams-using-msi"></a>Installieren von Microsoft Teams mithilfe eines MSI-Pakets
=================================

> [!Tip]
> Sehen Sie sich die folgenden Sitzung auf Informationen zu den Vorteilen von der Windows-Desktop-Client, wie es geplant und wie diese bereitgestellt: [Teams Windows Desktop Client](https://aka.ms/teams-clients)

Verwendung von System Center Configuration Manager oder Gruppenrichtlinien oder Drittanbieter-Verteilungsmechanismen für umfassenden Bereitstellung hat Microsoft MSI-Dateien ( [32-Bit-](https://aka.ms/teams32bitmsi) und [64-Bit](https://aka.ms/teams64bitmsi)) bereitgestellt, mit denen Administratoren für die Bereitstellung von Teams Massen können wählen Benutzer oder Computer. Diese Dateien können Administratoren Remotebereitstellung Teams, damit Benutzer keine die app Teams manuell herunterladen. Bei der Bereitstellung automatisch Teams werden Einführung für alle Benutzer, die auf diesem Computer anmelden. (Sie können Automatisches Starten nach der Installation der app deaktivieren. [Finden Sie weiter unten](#disable-auto-lanuch-for-the-msi-installer).) Es wird empfohlen, dass Sie das Paket auf dem Computer bereitzustellen, sodass alle neuen Benutzer des Computers auch von dieser Bereitstellung profitieren. 
 
> [!Note] 
> Weitere Informationen zu SCCM finden Sie unter [Einführung zu System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Bereitstellungsverfahren (empfohlen)
1. Rufen Sie das neueste-Paket.
2. Verwenden Sie die Standardeinstellungen, durch die MSI-Datei vorausgefüllt.
3. Bereitstellen Sie auf Computern, wenn möglich.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funktionsweise von Microsoft-Teams MSI-Paket

Die Teams MSI-Datei wird Program Files ein Installationsprogramm versehen. Wenn ein Benutzer ein neues Windows-Benutzerprofil anmeldet, das Installationsprogramm wird gestartet, und eine Kopie der Anwendung Teams im Anwendungsdaten-Ordner des Benutzers installiert werden. Wenn ein Benutzer bereits die Teams app im Ordner Anwendungsdaten installiert hat, wird der MSI-Installer den Prozess für diesen Benutzer übersprungen.

Verwenden Sie die MSI-Datei nicht zum Bereitstellen von Updates, da der Client Update automatisch wird, wenn es erkennt, dass eine neue Version aus dem Dienst verfügbar ist. Verwenden Sie erneut bereitstellen, um der neueste Version von Installer den Prozess der erneutes Bereitstellen von MSI-Datei weiter unten beschriebenen.Wenn Sie eine ältere Version von MSI-Paket bereitstellen, den Client wird automatisch nach Möglichkeit für den Benutzer aktualisieren. Wenn eine sehr alte Version bereitgestellt, ruft ab, wird die MSI-Datei eine Anwendung Aktualisierung auszulösen, bevor der Benutzer Teams nutzen kann. 

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
> [Bereitstellung von Microsoft-Teams, bereinigen Sie](scripts/Powershell-script-teams-deployment-clean-up.md) Skript können Sie die Schritte 1 und 2 über SCCM erreichen.    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a>Automatisches Starten für die MSI-Installer deaktivieren

Standardverhalten der die MSI-Datei ist, installieren Sie den Client Teams, sobald ein Benutzer anmeldet, und anschließend Teams automatisch starten. Sie können dieses Verhalten mit den Parametern unter wie folgt ändern:

- Wenn ein Benutzer in Windows anmeldet, werden die Teams mit der MSI-Datei installiert werden
- Jedoch wird der Client Teams nicht gestartet werden, bis der Benutzer Teams manuell gestartet wurde
- Eine Verknüpfung zum Starten von Teams wird auf dem Desktop des Benutzers hinzugefügt werden
- Nachdem manuell gestartet, Teams werden automatisch gestartet werden, wenn der Benutzer angemeldet

Für 32-Bit-version
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Für die 64-Bit-version
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```
> [!Note] 
>  Wenn Sie die MSI-Datei manuell ausführen, müssen Sie es mit erhöhten Berechtigungen ausführen. Auch wenn Sie es als Administrator Ausführen ohne mit erhöhten Berechtigungen ausführen, wird das Installationsprogramm nicht die Option zum Deaktivieren der automatischen Start konfiguriert sein.
