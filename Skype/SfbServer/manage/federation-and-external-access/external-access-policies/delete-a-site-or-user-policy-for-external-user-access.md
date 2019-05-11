---
title: Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können eine beliebige Standort- oder Benutzerrichtlinie löschen, die in der Skype für Business Server-Systemsteuerung auf der Seite Richtlinie für den externen Zugriff aufgeführt ist.
ms.openlocfilehash: 517c5b015d4e2fe5de584a8079af1bb4f5ed248a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920417"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff

Wenn Sie erstellt oder konfiguriert Richtlinien für den externen Benutzerzugriff, die Sie nicht mehr verwenden möchten, können Sie Folgendes:

  - Löschen Sie alle Standort- oder Benutzerrichtlinie, die Sie erstellt haben.

  - Die globale Richtlinie auf die Standardeinstellungen zurückgesetzt. Die Standardeinstellungen für die globale Richtlinie verweigern keinen Zugriff externer Benutzer. Die globale Richtlinie kann nicht gelöscht werden.


Sie können eine beliebige Standort- oder Benutzerrichtlinie löschen, die in der Skype für Business Server-Systemsteuerung auf der Seite **Richtlinie für den externen Zugriff** aufgeführt ist. Löschen die globale Richtlinie nicht tatsächlich gelöscht, jedoch wird es nur auf die Standardeinstellungen, die Unterstützung für externe Benutzer Zugriffsoptionen nicht enthalten. Ausführliche Informationen zum Zurücksetzen der globalen Richtlinie finden Sie unter [Zurücksetzen der globalen Richtlinie für den Zugriff externer Benutzer](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>So löschen Sie eine Standort- oder Benutzerrichtlinie für den Zugriff externer Benutzer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie auf **Zugriff durch externe Benutzer**, klicken Sie auf **Richtlinie für den externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die Standort- oder Benutzerrichtlinie zu löschen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

5.  Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Entfernen der PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets

Richtlinien für externen Zugriff können mithilfe von Windows PowerShell und Remove-CsExternalAccessPolicy-Cmdlet gelöscht werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 


## <a name="to-remove-a-specific-external-access-policy"></a>So entfernen eine bestimmte externe Zugriffsrichtlinie

  - Dieser Befehl entfernt die externe Zugriffsrichtlinie, die auf den Standort Redmond angewendet:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>So entfernen Sie alle externen Zugriff auf der Benutzerebene angewendete Richtlinien

  - Mit diesem Befehl werden alle externen Richtlinien für den Zugriff auf der Benutzerebene konfigurierte entfernt:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Um alle Richtlinien für den externen Zugriff zu entfernen, in denen externe Benutzerzugriff deaktiviert ist

  - Dieser Befehl löscht alle Richtlinien den externen Zugriff, in dem externe Benutzerzugriff deaktiviert ist:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Weitere Informationen finden Sie im Hilfethema zum [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) -Cmdlet.
