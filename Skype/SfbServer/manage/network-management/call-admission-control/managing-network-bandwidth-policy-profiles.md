---
title: Verwalten von Netzwerk-bandbreitenrichtlinienprofilen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen, erstellen, ändern oder Löschen von Netzwerk-bandbreitenrichtlinienprofilen.
ms.openlocfilehash: d27e4df1b549afd3c176f8b54453c44bb97819f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878900"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Verwalten von Richtlinienprofilen für die Netzwerkbandbreite in Skype for Business Server

Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen, erstellen, ändern oder Löschen von Netzwerk-bandbreitenrichtlinienprofilen.

## <a name="view-network-bandwidth-policy-profile-information"></a>Netzwerkbandbreite Richtlinie Profilinformationen anzeigen

Im Rahmen der anrufsteuerung (CAC) wird eine bandbreitenrichtlinie bandbreiteneinschränkungen für bestimmte Modalitäten definiert. In Skype für Business Server können nur Audio- und Videodaten Modalitäten Netzwerkbandbreite ist eingeschränkt zugewiesen werden. Sie können allgemeine Netzwerkbandbreite ist eingeschränkt und Sitzung Einschränkungen festlegen. Die Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder Löschen eines Profils Container für diese Richtlinien. Jede bandbreitenrichtlinienprofil kann eine oder mehrere Netzwerkstandorte zugeordnet werden. Verwenden Sie die folgenden Verfahren, um ein bandbreitenrichtlinienprofil anzuzeigen. 

### <a name="to-view-a-bandwidth-policy-profile"></a>So zeigen Sie ein bandbreitenrichtlinienprofil an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Anzeigen der Netzwerk-Bandbreite Profil Richtlinieninformationen mithilfe von Windows PowerShell-cmdlets

Netzwerkbandbreite Profile können mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkBandwidthPolicyProfile angezeigt werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>So zeigen Sie Netzwerkbandbreite Richtlinie Profilinformationen an

  - Um Informationen über alle Ihre Richtlinienprofile anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Weitere Informationen finden Sie im Hilfethema zum [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) -Cmdlet.


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Erstellen oder Ändern von bandbreitenrichtlinienprofilen

Im Rahmen der anrufsteuerung (CAC) wird eine bandbreitenrichtlinie bandbreiteneinschränkungen für bestimmte Modalitäten definiert. In Skype für Business Server können nur Audio- und Videodaten Modalitäten Netzwerkbandbreite ist eingeschränkt zugewiesen werden. Sie können allgemeine Netzwerkbandbreite ist eingeschränkt und Sitzung Einschränkungen festlegen. Die Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder Löschen eines Profils Container für diese Richtlinien. Jede bandbreitenrichtlinienprofil kann eine oder mehrere Netzwerkstandorte zugeordnet werden. Verwenden Sie die folgenden Verfahren zum Erstellen oder ändern ein bandbreitenrichtlinienprofil. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Erstellen Sie ein neues bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf **neu**.

5.  Geben Sie im **Neuen Bandbreitenrichtlinienprofil**in das Feld **Name** einen Namen ein. Dieser Name muss für alle bandbreitenrichtlinienprofile eindeutig sein.

6.  Geben Sie im Feld **audiolimit** einen numerischen Wert ein. Dieser Wert ist die maximale Bandbreite für alle audioverbindungen, ausgedrückt in Kbit/s zugewiesen werden.

7.  Geben Sie einen numerischen Wert im Feld **Grenzwert für audiositzung** . Dieser Wert ist die maximale Bandbreite für eine einzelne audio Verbindung, ausgedrückt in Kbit/s zugewiesen werden. Dieser Wert muss es sich um 40 oder höher sein.

8.  Geben Sie einen numerischen Wert im Feld **videolimit** . Dieser Wert ist die maximale Bandbreite für alle videoverbindungen, ausgedrückt in Kbit/s zugewiesen werden.

9.  Geben Sie einen numerischen Wert im Feld **Grenzwert für videositzung** . Dieser Wert ist die maximale Bandbreite für eine einzelne video Verbindung, ausgedrückt in Kbit/s zugewiesen werden. Dieser Wert muss 100 oder höher sein.

10. (Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu diesem bandbreitenrichtlinienprofil bereitzustellen, die durch den Namen allein vermittelt werden können.

11. Klicken Sie auf **Commit ausführen**.

    > [!NOTE]  
    > Erstellen ein neues bandbreitenrichtlinienprofil erzwingt nicht automatisch Bandbreite Einschränkungen. Sie müssen zuerst das Richtlinienprofil einer Website zuordnen. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>So ändern Sie ein bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **Bandbreitenrichtlinienprofil bearbeiten** die Felder nach Bedarf (Weitere Informationen hierzu finden Sie unter [So erstellen Sie ein neues bandbreitenrichtlinienprofil](#to-create-a-new-bandwidth-policy-profile)).

7.  Klicken Sie auf **Commit ausführen**.

    > [!NOTE]  
    > Wenn Sie das bandbreitenrichtlinienprofil ändern, werden die bandbreiteneinschränkungen aller Netzwerkstandorte, die diesem bandbreitenrichtlinienprofil zugeordnet unmittelbar aktualisiert.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Löschen von Netzwerk-bandbreitenrichtlinienprofilen

Im Rahmen der anrufsteuerung (CAC) wird eine bandbreitenrichtlinie bandbreiteneinschränkungen für bestimmte Modalitäten definiert. In Skype für Business Server können nur Audio- und Videodaten Modalitäten Netzwerkbandbreite ist eingeschränkt zugewiesen werden. Sie können allgemeine Netzwerkbandbreite ist eingeschränkt und Sitzung Einschränkungen festlegen. Die Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder Löschen eines Profils Container für diese Richtlinien. Verwenden Sie die folgenden Verfahren, um ein Netzwerk-bandbreitenrichtlinienprofilen zu löschen. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>So löschen Sie ein bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehr als ein Profil zu einem Zeitpunkt löschen. Zu diesem Zweck, drücken Sie STRG, und wählen Sie bei gedrückter STRG-Taste mehrere Profile aus. Oder, um alle Profile ausgewählt haben, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.
   

    > [!WARNING]  
    > Ein bandbreitenrichtlinienprofil, das einem Netzwerkstandort zugeordnet ist, kann nicht gelöscht werden. Bevor Sie das Profil löschen können, müssen Sie zuerst die Zuordnung mit den Netzwerkstandort entfernen. 


## <a name="see-also"></a>Siehe auch

[Verwalten der anrufsteuerung für Standorte](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

