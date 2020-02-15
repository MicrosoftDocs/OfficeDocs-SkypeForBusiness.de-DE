---
title: Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Die globale Richtlinie kann nicht vollständig gelöscht werden. Bei Verwendung der Option **Löschen** für die globale Richtlinie wird die globale Richtlinie lediglich auf die Standardeinstellungen zurückgesetzt. In diesen Einstellungen ist die Unterstützung von Optionen für den externen Benutzerzugriff nicht aktiviert.
ms.openlocfilehash: acb275ac924dbb5b7e9ad377ab4d287a0734f752
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043657"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer in Skype for Business Server 

Wenn Sie Richtlinien für den externen Benutzer Zugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie folgende Aktionen ausführen:

  - Löschen Sie alle Website-oder Benutzerrichtlinien, die Sie erstellt haben.

  - Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück. Die standardmäßigen globalen Richtlinieneinstellungen verweigern den Zugriff durch externe Benutzer. Die globale Richtlinie kann nicht gelöscht werden.

Die globale Richtlinie kann nicht vollständig gelöscht werden. Bei Verwendung der Option **Löschen** für die globale Richtlinie wird die globale Richtlinie lediglich auf die Standardeinstellungen zurückgesetzt. In diesen Einstellungen ist die Unterstützung von Optionen für den externen Benutzerzugriff nicht aktiviert.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK**. Sie werden in einer Meldung im oberen Seitenbereich darüber informiert, dass die globale Richtlinie zurückgesetzt wurde.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets

Die globale Richtlinie für den externen Zugriff kann mit Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy zurückgesetzt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden. 

## <a name="to-reset-the-global-external-access-policy"></a>So setzen Sie die globale Richtlinie für den externen Zugriff zurück

  - Verwenden Sie den folgenden Befehl, um die globale Richtlinie für den externen Zugriff zurückzusetzen:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .


