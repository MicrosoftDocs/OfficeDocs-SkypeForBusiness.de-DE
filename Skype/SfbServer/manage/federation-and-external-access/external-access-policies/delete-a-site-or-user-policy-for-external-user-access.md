---
title: Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können alle Website- oder Benutzerrichtlinien löschen, die in der Skype for Business Server-Systemsteuerung auf der Seite Richtlinie für den externen Zugriff aufgeführt sind.
ms.openlocfilehash: 407e90af201055f371dc92485ab258bac851a258
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099021"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff

Wenn Sie richtlinien für den externen Benutzerzugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie die folgenden Schritte tun:

  - Löschen Sie alle von Ihnen erstellten Website- oder Benutzerrichtlinien.

  - Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück. Die standardmäßigen globalen Richtlinieneinstellungen verweigern externen Benutzern den Zugriff. Die globale Richtlinie kann nicht gelöscht werden.


Sie können alle Website- oder Benutzerrichtlinien löschen, die in der Skype for Business Server-Systemsteuerung auf der Seite Richtlinie für den **externen Zugriff aufgeführt** sind. Beim Löschen der globalen Richtlinie wird sie nicht tatsächlich gelöscht, sondern nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen enthalten. Weitere Informationen zum Zurücksetzen der globalen Richtlinie finden Sie unter [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>So löschen Sie eine Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über entsprechende Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie auf **Externer Benutzerzugriff** und dann auf **Richtlinie für den externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die zu löschende Standort- oder Benutzerrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Entfernen von PIN-Richtlinien mithilfe Windows PowerShell Cmdlets

Richtlinien für den externen Zugriff können mithilfe von Windows PowerShell und dem cmdlet Remove-CsExternalAccessPolicy gelöscht werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>So entfernen Sie eine bestimmte Richtlinie für den externen Zugriff

  - Dieser Befehl entfernt die Richtlinie für den externen Zugriff, die auf den Standort "Redmond" angewendet werden:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>So entfernen Sie alle richtlinien für den externen Zugriff, die auf den Benutzerbereich angewendet werden

  - Dieser Befehl entfernt alle Richtlinien für den externen Zugriff, die auf Benutzerbasis konfiguriert wurden:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>So entfernen Sie alle Richtlinien für den externen Zugriff, bei denen der Zugriff durch externe Benutzer deaktiviert ist

  - Dieser Befehl löscht alle Richtlinien für den externen Zugriff, für die der externe Benutzerzugriff deaktiviert ist:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)