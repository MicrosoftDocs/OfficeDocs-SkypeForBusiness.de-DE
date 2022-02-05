---
title: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff
ms.reviewer: null
'ms:assetid': 8207e1b1-de9e-461f-975f-fcc5c526849a
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)'
'ms:contentKeyID': 48184675
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Sie können eine globale Richtlinie nicht vollständig löschen. Wenn Sie die Option **"Löschen"** in der globalen Richtlinie verwenden, wird die globale Richtlinie nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen enthalten.'
---


# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Zurücksetzen der globalen Richtlinie für den Externen Benutzerzugriff in Skype for Business Server 

Wenn Sie richtlinien für den externen Benutzerzugriff erstellt oder konfiguriert haben, die Sie nicht mehr verwenden möchten, können Sie die folgenden Methoden verwenden:

  - Löschen Sie alle Website- oder Benutzerrichtlinien, die Sie erstellt haben.

  - Setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück. Die standardmäßigen globalen Richtlinieneinstellungen verweigern externen Benutzern den Zugriff. Die globale Richtlinie kann nicht gelöscht werden.

Sie können eine globale Richtlinie nicht vollständig löschen. Die Option **"Löschen"** in der globalen Richtlinie setzt nur die globale Richtlinie auf die Standardeinstellungen zurück, die keine Unterstützung für Zugriffsoptionen für externe Benutzer enthalten.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist oder über entsprechende Benutzerrechte verfügt oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK**. Sie werden in einer Meldung im oberen Seitenbereich darüber informiert, dass die globale Richtlinie zurückgesetzt wurde.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe Windows PowerShell Cmdlets

Die globale Richtlinie für den externen Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy zurückgesetzt werden. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausführen. 

## <a name="to-reset-the-global-external-access-policy"></a>So setzen Sie die globale Richtlinie für den externen Zugriff zurück

  - Verwenden Sie den folgenden Befehl, um die globale Richtlinie für den externen Zugriff zurückzusetzen:<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) ".
