---
title: Verwalten von Netzwerkbandbreite-Richtlinienprofilen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um Netzwerkbandbreite-Richtlinienprofile anzuzeigen, zu erstellen, zu ändern oder zu löschen.
ms.openlocfilehash: 3b2b62e5e823a9d86f1884d79b67483bce38a39f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279522"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Verwalten von Richtlinienprofilen für die Netzwerkbandbreite in Skype for Business Server

Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um Netzwerkbandbreite-Richtlinienprofile anzuzeigen, zu erstellen, zu ändern oder zu löschen.

## <a name="view-network-bandwidth-policy-profile-information"></a>Profilinformationen zu Netzwerkbandbreite-Richtlinien anzeigen

Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen. In Skype for Business Server können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen. Sie können das Skype for Business Server Control Panel verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Jedes bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet sein. Gehen Sie wie folgt vor, um ein bandbreitenrichtlinienprofil anzuzeigen. 

### <a name="to-view-a-bandwidth-policy-profile"></a>So zeigen Sie ein bandbreitenrichtlinienprofil an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Profilinformationen für die Netzwerkbandbreite mithilfe von Windows PowerShell-Cmdlets

Netzwerkbandbreiten Profile können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkBandwidthPolicyProfile angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>So zeigen Sie Profilinformationen zu Netzwerkbandbreiten an

  - Wenn Sie Informationen zu allen Netzwerkbandbreite-Richtlinienprofilen anzeigen möchten, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Erstellen oder Ändern von Bandbreitenrichtlinien Profilen

Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen. In Skype for Business Server können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen. Sie können das Skype for Business Server Control Panel verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Jedes bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet sein. Gehen Sie wie folgt vor, um ein bandbreitenrichtlinienprofil zu erstellen oder zu ändern. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>So erstellen Sie ein neues bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite mit den **Bandbreitenrichtlinien** auf **neu**.

5.  Geben Sie in **Neues bandbreitenrichtlinienprofil**einen Namen in das Feld **Name** ein. Dieser Name muss unter allen Bandbreitenrichtlinien Profilen eindeutig sein.

6.  Geben Sie **** im Feld audiogrenze einen numerischen Wert ein. Dieser Wert ist die maximale Bandbreite, die für alle Audioverbindungen reserviert werden soll, ausgedrückt in Kbit/s.

7.  Geben Sie einen numerischen Wert in das Feld "audiositzungs **Limit** " ein. Dieser Wert ist die maximale Bandbreite, die für eine einzelne Audioverbindung reserviert werden soll, ausgedrückt in Kbit/s. Dieser Wert muss 40 oder höher sein.

8.  Geben Sie einen numerischen Wert in das Feld **Video Grenzwert** ein. Dieser Wert ist die maximale Bandbreite, die für alle Videoverbindungen reserviert werden soll, ausgedrückt in Kbit/s.

9.  Geben Sie einen numerischen Wert in das Feld **Video Session Limit** ein. Dieser Wert ist die maximale Bandbreite, die für eine einzelne Videoverbindung reserviert werden soll, ausgedrückt in Kbit/s. Dieser Wert muss 100 oder höher sein.

10. Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu diesem bandbreitenrichtlinienprofil bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.

11. Klicken Sie auf **Commit ausführen**.

    > [!NOTE]  
    > Durch das Erstellen eines neuen bandbreitenrichtlinienprofils werden keine Bandbreiteneinschränkungen automatisch erzwungen. Sie müssen zuerst das Richtlinienprofil einer Website zuordnen. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>So ändern Sie ein bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **bandbreitenrichtlinienprofil bearbeiten** die Felder nach Bedarf (Details finden Sie unter so wird es gemacht: [Erstellen eines neuen bandbreitenrichtlinienprofils](#to-create-a-new-bandwidth-policy-profile)).

7.  Klicken Sie auf **Commit ausführen**.

    > [!NOTE]  
    > Wenn Sie das bandbreitenrichtlinienprofil ändern, werden die Bandbreiteneinschränkungen für alle Netzwerk Websites, die diesem bandbreitenrichtlinienprofil zugeordnet sind, sofort aktualisiert.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Löschen von Netzwerkbandbreite-Richtlinienprofilen

Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen. In Skype for Business Server können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen. Sie können das Skype for Business Server Control Panel verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Gehen Sie wie folgt vor, um ein Netzwerkband breiten Richtlinienprofil zu löschen. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>So löschen Sie ein bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehr als ein Profil gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Profile aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Profile auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alles auswählen** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.
   

    > [!WARNING]  
    > Sie können ein bandbreitenrichtlinienprofil, das einer Netzwerk Website zugeordnet ist, nicht löschen. Sie müssen zuerst die Zuordnung zur Netzwerk Website entfernen, bevor Sie das Profil löschen können. 


## <a name="see-also"></a>Siehe auch

[Verwalten der Anrufsteuerung für Websites](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

