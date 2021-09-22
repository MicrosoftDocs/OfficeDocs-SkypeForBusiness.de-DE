---
title: Einrichtung von Administratoren für die Edu Microsoft Parents-App
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 'Microsoft Teams für EDU-Artikel : Dokumentvoraussetzungen und PowerShell-Einrichtung für die Eltern-App.'
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475908"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Bereitstellen der Eltern-App in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Das Aktivieren der Eltern-App in Microsoft Teams ist ein einfacher Prozess für Administratoren, der eine sichere Methode für Lehrkräfte bietet, mit der sie mit Schülern/Studenten und ihren Kontakten kommunizieren können, die weiterhin Mandanten sind und auf die gesamte Organisation der Lehrkräfte skaliert wird.

## <a name="requirements"></a>Anforderungen

- SDS (School data sync) – Sie müssen verwandte Kontakte, die mit Ihren Schülern/Studenten verknüpft sind, mithilfe der CSV-Option auf SDS hochladen. Weitere Informationen finden Sie unter Konfigurieren von CSV für [SDS](/schooldatasync/set-up-your-sds-flow) und [Aktualisieren](/graph/api/relatedcontact-update) verwandter Kontakte.
- In Teams Admin Center muss der Kursbesitzer **Chat** aktiviert haben, und **Partnerchat** mit Teams Konten, die nicht von **einer Organisation verwaltet werden.**

Wenn Sie Den Partnerchat pro Benutzer aktivieren müssen, sind die schritte unten aufgeführt.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Aktivieren von Partnerchats pro Benutzer

1. Installieren Sie die neueste Microsoft Teams PowerShell-Modulvorschau.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. Führen Sie die Ausführung in einem Befehlsfenster mit Anmeldeinformationen aus, die über Administratorrechte verfügen.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. Aktivieren und deaktivieren Sie dies in der Konfiguration auf Gruppen-/Benutzerebene oder auf Mandantenebene.

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > Beim Ausführen dieser PowerShell kann es eine Stunde oder mehr dauern, bis Änderungen abgeschlossen sind.
    
## <a name="more-information"></a>Weitere Informationen

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Zuweisen der Richtlinie zu einem Benutzer](/powershell/module/skype/grant-csexternalaccesspolicy)
