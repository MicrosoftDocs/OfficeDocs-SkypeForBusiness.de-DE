---
title: Cmdlets in Skype for Business Online, die den Parameter "Mandant" verwenden
description: Cmdlets in Skype for Business Online, die den Parameter Mandanten verwenden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546801"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>Cmdlets in Skype for Business Online, die den Parameter "Mandant" verwenden

 


Wenn Sie Ihre Einstellungen für öffentliche Anbieter ändern, müssen Sie immer eine Mandanten Identität angeben. Dies gilt auch dann, wenn Sie nur einen einzigen Mandanten haben. Mit dem folgenden Befehl wird beispielsweise Windows Live als einziger öffentlicher Anbieter festgelegt, mit dem Ihre Benutzer kommunizieren können:

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

Glücklicherweise müssen Sie nicht jedes Mal, wenn Sie eines dieser Cmdlets ausführen, die Mandanten-ID eingeben (beispielsweise bf19b7db-6960-41e5-A139-2aa373474354). Stattdessen können Sie die Mandanten-ID abrufen, indem Sie das Cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) ausführen, die Mandanten-ID in einer Variablen speichern und diese Variable dann verwenden, wenn Sie eines der anderen Cmdlets aufrufen. Zum Beispiel:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

Alternativ können Sie dies in einem einzigen Befehl durchführen, indem Sie die Mandanten-ID abrufen und diesen Wert anschließend an das Set-CsTenantPublicProvider-Cmdlet weiterleiten:

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

Sie müssen die Mandanten-ID nicht angeben, wenn Sie das **Get-CsTenant-** Cmdlet aufrufen. Dieser Befehl gibt Informationen zu Ihrem Mandanten zurück:

    Get-CsTenant

Die folgenden Cmdlets akzeptieren eine Mandanten Identität. In diesen Fällen ist der Parameter jedoch optional und muss beim Aufruf des Cmdlets nicht eingegeben werden. Stattdessen werden Windows PowerShell die Mandanten Identität basierend auf dem Skype for Business Online Mandanten, mit dem Sie derzeit verbunden sind, effektiv eingeben:

  - [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [Gruppe-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [Gruppe-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

Beispielsweise kann das **Get-CsTenantFederationConfiguration-** Cmdlet mithilfe dieses Befehls aufgerufen werden:

    Get-CsTenantFederationConfiguration

Obwohl dies nicht erforderlich ist, können Sie den Parameter Mandanten einschließen, wenn Sie Get-CsTenantFederationConfiguration aufrufen:

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

