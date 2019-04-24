---
title: Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Beim Konfigurieren von Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern wenden Sie die Richtlinien für Benutzer von Partnerdomänen. '
ms.openlocfilehash: df5702fb217d238a26a8a9975e7e4a0792787399
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199898"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzer in Skype für Business Server

Beim Konfigurieren von Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern wenden Sie die Richtlinien für Benutzer von Partnerdomänen. Sie können eine oder mehrere externe Benutzer Zugriffsrichtlinien zur Steuerung konfigurieren, ob Benutzer von Partnerdomänen mit Ihrer Skype für Business Server-Benutzer zusammenarbeiten können. Zur Steuerung des Zugriffs Verbundbenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren. Skype für Business Server aufgeführt, die auf einer Richtlinienebene angewendet werden kann Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.


> [!NOTE]  
> Auch wenn Sie nicht den Verbund für Ihre Organisation aktiviert haben, können Sie Richtlinien zum Steuern der partnerbenutzerzugriff, konfigurieren. Die Richtlinien, die Sie konfigurieren, werden jedoch in Kraft nur, wenn Sie den Verbund für Ihre Organisation aktiviert sein. Ausführliche Informationen zur Aktivierung des Verbunds finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md).  Wenn Sie eine Benutzerrichtlinie zur Steuerung des Zugriffs Verbundbenutzer angeben, gilt die Richtlinie darüber hinaus nur für Benutzer, die für Skype für Business Server aktiviert und so konfiguriert, dass die Richtlinie verwenden.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** eine der folgenden Aktionen aus:
    
      - Um die globale Richtlinie zur Unterstützung der partnerbenutzerzugriff zu konfigurieren, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
      - Erstellen einer neuen Standortrichtlinie, klicken Sie auf **neu**, und klicken Sie dann auf **Standortrichtlinie**. Klicken Sie im **Dialogfeld Standort auswählen**auf den geeigneten Standort aus der Liste aus, und klicken Sie dann auf **OK**.
    
      - Um eine neue Richtlinie zu erstellen, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in **Neue Richtlinie für den externen Zugriff**einen eindeutigen Namen im Feld **Name** , das angibt, welche Benutzer Richtlinie Hintergrund (beispielsweise **EnableFederatedUsers** für eine Benutzerrichtlinie, mit dem verbunddomäne Benutzern können).
    
      - Um eine vorhandene Richtlinie zu ändern, klicken Sie auf die entsprechende Richtlinie in der Tabelle, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  (Optional) Wenn Sie hinzufügen oder bearbeiten eine Beschreibung möchten, geben Sie die Informationen für die Richtlinie im Feld **Beschreibung**.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Um den partnerbenutzerzugriff für die Richtlinie zu aktivieren, aktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** .
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** , um den partnerbenutzerzugriff für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

Um partnerbenutzerzugriff zu aktivieren, müssen Sie auch Unterstützung für den Verbund in Ihrer Organisation aktivieren. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Ist dies eine Benutzerrichtlinie, müssen Sie auch die Richtlinie für Benutzer anwenden, die für die Zusammenarbeit mit Verbundbenutzer enthalten sein sollen. Weitere Informationen hierzu finden Sie unter [Zuweisen eine Richtlinie für den externen Benutzerzugriff](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>So konfigurieren Sie eine vorhandene Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

3.  Geben Sie Folgendes in die Skype für Business Server-Verwaltungsshell:
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Der Parameter "EnablePublicCloudAudioVideoAccess" weist eine entsprechende Auswahl in der Skype Business Server-Systemsteuerung keinen


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Zum Erstellen einer neuen Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

3.  Geben Sie Folgendes in die Skype für Business Server-Verwaltungsshell:
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Ein Beispiel zum Erstellen einer neuen Standortrichtlinie:
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Löschen oder Zurücksetzen eine Richtlinie mit Windows PowerShell für Zugriff durch Benutzer von Partnerdomänen zu unterstützen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Geben Sie Folgendes in die Skype für Business Server-Verwaltungsshell
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Ein Beispiel für das Zurücksetzen der globalen Richtlinie (die globale Richtlinie kann nur müssen die Einstellung entfernt wurden. Die Richtlinie kann nicht gelöscht werden):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Um eine Standortrichtlinie zu entfernen, geben Sie Folgendes ein:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Die Richtlinien für den Standort "Redmond" gelöscht. Um eine Benutzerrichtlinie mit dem Namen UserEAPPolicy zu löschen, geben Sie Folgendes ein:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Siehe auch


[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer](assign-an-external-user-access-policy.md)

[Verwalten von SIP-Partnerdomänen für eine Organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Verwalten von SIP-Partnerverbundanbietern für eine Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Neue CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[GRANT-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

