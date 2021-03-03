---
title: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Die globale Richtlinie kann nicht vollständig gelöscht werden. Bei Verwendung der Option **Löschen** für die globale Richtlinie wird die globale Richtlinie lediglich auf die Standardeinstellungen zurückgesetzt. In diesen Einstellungen ist die Unterstützung von Optionen für den externen Benutzerzugriff nicht aktiviert.
ms.openlocfilehash: be4f99c5b98ca46e7fed57781cf1661a2755a4ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817245"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff in Skype for Business Server 

Wenn Sie Richtlinien für den externen Benutzerzugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie die folgenden Schritte tun:

  - Löschen Sie alle von Ihnen erstellten Website- oder Benutzerrichtlinien.

  - Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück. Die globalen Standardrichtlinieneinstellungen verweigern den Zugriff durch externe Benutzer. Die globale Richtlinie kann nicht gelöscht werden.

Die globale Richtlinie kann nicht vollständig gelöscht werden. Bei Verwendung der Option **Löschen** für die globale Richtlinie wird die globale Richtlinie lediglich auf die Standardeinstellungen zurückgesetzt. In diesen Einstellungen ist die Unterstützung von Optionen für den externen Benutzerzugriff nicht aktiviert.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK**. Sie werden in einer Meldung im oberen Seitenbereich darüber informiert, dass die globale Richtlinie zurückgesetzt wurde.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe Windows PowerShell Cmdlets

Die globale Richtlinie für den externen Zugriff kann mithilfe von Windows PowerShell und dem cmdlet Remove-CsExternalAccessPolicy zurückgesetzt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>So setzen Sie die globale Richtlinie für den externen Zugriff zurück

  - Verwenden Sie den folgenden Befehl, um die globale Richtlinie für den externen Zugriff zurückzusetzen:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsExternalAccessPolicy".](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)


