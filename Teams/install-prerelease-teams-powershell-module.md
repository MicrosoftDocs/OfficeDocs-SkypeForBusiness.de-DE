---
title: Installieren der Pre-Release-Version des Teams PowerShell-Moduls
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Führen Sie die folgenden Schritte aus, um die Vorabversion des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu installieren.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321768"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>Installieren der Pre-Release-Version des Teams PowerShell-Moduls

In diesem Artikel wird beschrieben, wie Sie die neueste Vorabversion des Teams PowerShell-Moduls aus dem [PowerShell-Test Katalog](https://www.poshtestgallery.com/packages/MicrosoftTeams/)installieren. Sie benötigen die Vorabversion des Teams PowerShell-Moduls in Szenarien, in denen Cmdlets für die Verwaltung eines Teams-Features in der allgemein verfügbaren Version des Moduls nicht unterstützt werden und nur in der Pre-Release-Version verfügbar sind.

Führen Sie die folgenden Schritte aus, um die neueste Vorabversion des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu installieren.

> [!NOTE]
> Installieren Sie das Teams PowerShell-Modul nicht aus dem PowerShell-Test Katalog parallel mit einer Version des Moduls aus dem [öffentlichen PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams/). Führen Sie die folgenden Schritte aus, um das Team-PowerShell-Modul zunächst aus dem öffentlichen PowerShell-Katalog zu deinstallieren und dann die neueste Version des Moduls aus dem PowerShell-Test Katalog zu installieren.

1. Schließen Sie alle vorhandenen PowerShell-Sitzungen.
2. Starten Sie eine neue Instanz des Windows PowerShell-Moduls.
3. Führen Sie die folgenden Schritte aus, um das PowerShell-Modul von Teams aus dem öffentlichen PowerShell-Katalog zu deinstallieren:

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Schließen Sie alle vorhandenen PowerShell-Sitzungen.
5. Starten Sie das Windows PowerShell-Modul erneut, und führen Sie dann die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren:

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Führen Sie die folgenden Schritte aus, um das neueste Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren:

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Aktualisieren auf die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog

Wenn Sie das Teams PowerShell-Modul bereits aus dem PowerShell-Test Katalog installiert haben, führen Sie die folgenden Schritte aus, um auf die neueste Version zu aktualisieren.

1. Schließen Sie alle vorhandenen PowerShell-Sitzungen.
2. Starten Sie eine neue Instanz des Windows PowerShell-Moduls.
3. Führen Sie die folgenden Schritte aus, um die aktuell installierte Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu aktualisieren:

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
