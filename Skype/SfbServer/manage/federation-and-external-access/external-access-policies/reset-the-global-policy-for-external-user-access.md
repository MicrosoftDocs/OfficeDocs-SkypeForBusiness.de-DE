---
title: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine globale Richtlinie kann nicht vollständig gelöscht werden. Mit der Option **Löschen** auf die globale Richtlinie setzt nur die globale Richtlinie auf die Standardeinstellungen, die keine Unterstützung für externe Benutzer Zugriffsoptionen enthalten.
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877874"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Zurücksetzen der globalen Richtlinie für den Zugriff externer Benutzer in Skype für Business Server 

Wenn Sie erstellt oder konfiguriert Richtlinien für den externen Benutzerzugriff, die Sie nicht mehr verwenden möchten, können Sie Folgendes:

  - Löschen Sie alle Standort- oder Benutzerrichtlinie, die Sie erstellt haben.

  - Die globale Richtlinie auf die Standardeinstellungen zurückgesetzt. Die Standardeinstellungen für die globale Richtlinie verweigern keinen Zugriff externer Benutzer. Die globale Richtlinie kann nicht gelöscht werden.

Eine globale Richtlinie kann nicht vollständig gelöscht werden. Mit der Option **Löschen** auf die globale Richtlinie setzt nur die globale Richtlinie auf die Standardeinstellungen, die keine Unterstützung für externe Benutzer Zugriffsoptionen enthalten.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste klicken Sie auf **Zugriff durch externe Benutzer**, klicken Sie auf **Richtlinie für den externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Löschen**.

5.  Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**. Am oberen Rand der Seite, die Sie darüber informiert, dass die globale Richtlinie zurückgesetzt wurde, wird eine Meldung angezeigt.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Zurücksetzen der globalen externe Zugriffsrichtlinie mithilfe von Windows PowerShell-Cmdlets

Die globale externe Zugriffsrichtlinie kann mithilfe von Windows PowerShell und Remove-CsExternalAccessPolicy-Cmdlet zurückgesetzt werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Windows PowerShell-Remotesitzung ausgeführt werden. 

## <a name="to-reset-the-global-external-access-policy"></a>Zurücksetzen die globalen externe Zugriffsrichtlinie

  - Mit diesem Befehl werden die globalen externe Zugriffsrichtlinie zurückgesetzt:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) -Cmdlet.


