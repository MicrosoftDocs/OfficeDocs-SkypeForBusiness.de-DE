---
title: Löschen einer Standort-oder Benutzerrichtlinie für den Zugriff durch externe Benutzer
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können eine beliebige Website-oder Benutzerrichtlinie löschen, die in der Skype for Business Server-Systemsteuerung auf der Seite Richtlinie für den externen Zugriff aufgeführt ist.
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041234"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Löschen einer Standort-oder Benutzerrichtlinie für den Zugriff durch externe Benutzer

Wenn Sie Richtlinien für den externen Benutzer Zugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie folgende Aktionen ausführen:

  - Löschen Sie alle Website-oder Benutzerrichtlinien, die Sie erstellt haben.

  - Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück. Die standardmäßigen globalen Richtlinieneinstellungen verweigern den Zugriff durch externe Benutzer. Die globale Richtlinie kann nicht gelöscht werden.


Sie können eine beliebige Website-oder Benutzerrichtlinie löschen, die in der Skype for Business Server-Systemsteuerung auf der Seite **Richtlinie für den externen Zugriff** aufgeführt ist. Wenn Sie die globale Richtlinie löschen, wird Sie nicht tatsächlich gelöscht, sondern nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen enthalten. Ausführliche Informationen zum Zurücksetzen der globalen Richtlinie finden Sie unter [Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>So löschen Sie eine Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie auf **Externer Benutzerzugriff** und dann auf **Richtlinie für den externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die zu löschende Standort- oder Benutzerrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Entfernen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets

Richtlinien für den externen Zugriff können mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy gelöscht werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 


## <a name="to-remove-a-specific-external-access-policy"></a>So entfernen Sie eine bestimmte Richtlinie für den externen Zugriff

  - Dieser Befehl entfernt die Richtlinie für den externen Zugriff, die auf den Standort "Redmond" angewendet werden:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>So entfernen Sie alle auf Benutzerebene angewendeten Richtlinien für den externen Zugriff

  - Dieser Befehl entfernt alle Richtlinien für den externen Zugriff, die auf Benutzerbasis konfiguriert wurden:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>So entfernen Sie alle externen Zugriffsrichtlinien, bei denen der Zugriff außerhalb des Benutzers deaktiviert ist

  - Dieser Befehl löscht alle Richtlinien für den externen Zugriff, für die der externe Benutzerzugriff deaktiviert ist:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .
