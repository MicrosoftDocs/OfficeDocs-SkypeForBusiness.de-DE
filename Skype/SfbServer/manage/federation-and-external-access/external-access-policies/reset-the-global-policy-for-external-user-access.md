---
title: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Es ist nicht möglich, eine globale Richtlinie vollständig zu löschen. Wenn Sie die Option " **Löschen** " in der globalen Richtlinie verwenden, wird die globale Richtlinie nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen beinhalten.
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280145"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer in Skype for Business Server 

Wenn Sie Richtlinien für den externen Benutzer Zugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie die folgenden Aktionen ausführen:

  - Löschen Sie alle von Ihnen erstellten Websites oder Benutzerrichtlinien.

  - Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück. Die globalen Standardrichtlinieneinstellungen verweigern den Zugriff externer Benutzer. Die globale Richtlinie kann nicht gelöscht werden.

Es ist nicht möglich, eine globale Richtlinie vollständig zu löschen. Wenn Sie die Option " **Löschen** " in der globalen Richtlinie verwenden, wird die globale Richtlinie nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen beinhalten.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Richtlinie für den externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Löschen**.

5.  Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**. Oben auf der Seite wird eine Meldung angezeigt, in der Sie darüber informiert werden, dass die globale Richtlinie zurückgesetzt wurde.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets

Die globale Richtlinie für den externen Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy zurückgesetzt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden. 

## <a name="to-reset-the-global-external-access-policy"></a>So setzen Sie die globale Richtlinie für den externen Zugriff zurück

  - Mit diesem Befehl wird die globale Richtlinie für den externen Zugriff zurückgesetzt:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


