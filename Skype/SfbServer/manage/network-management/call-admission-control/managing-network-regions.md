---
title: Verwalten von netzwerkregionen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Netzwerk Region * sind die Netzwerk-Hubs oder Backbones in der Konfiguration des Call Admission Control, E9-1-1 und medienumgehung verwendet.
ms.openlocfilehash: ea574fe981af679e4d841d786daf04460d1fb7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877629"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Verwalten von Netzwerkregionen in Skype for Business Server

*Netzwerkregionen* sind die Netzwerk-Hubs oder Backbones in der Konfiguration des Call Admission Control, E9-1-1 und medienumgehung verwendet. Verwenden Sie die folgenden Verfahren, um anzuzeigen, erstellen oder Ändern von netzwerkregionen. Angenommen, wenn Sie bereits von netzwerkregionen für eine VoIP-Funktion erstellt haben, müssen nicht Sie neue netzwerkregionen zu erstellen; andere erweiterten Enterprise-VoIP-Funktionen werden die gleichen netzwerkregionen verwenden. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben. 

Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen von Informationen zur netzwerkregion oder erstellen, ändern oder Löschen von netzwerkregionen. 

## <a name="view-network-region-information"></a>Anzeigen von Informationen zur netzwerkregion 


Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche. Jeder netzwerkregion muss mit einem zentralen Standort zugeordnet werden. Am zentrale Standort ist der Data Center-Website auf dem Call Admission Control (, CAC)-bandbreitenrichtliniendienst ausgeführt wird. Sie können Skype Business Server-Systemsteuerung verwenden, um netzwerkregionen anzuzeigen. Netzwerkregionen umfassen Einstellungen, die bestimmen, ob alternative Pfade über das Internet für Audio- und videoverbindungen zulässig sind. Verwenden Sie dieses Thema, um vorhandene netzwerkregionen anzuzeigen. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Zum Anzeigen von Informationen über eine netzwerkregion mit Skype Business Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, den, die Sie anzeigen möchten.
  
    > [!NOTE]  
    > Sie können jeweils nur eine Region anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zur netzwerkregion mithilfe von Windows PowerShell-cmdlets

Sie können Informationen zur netzwerkregion mithilfe von Windows PowerShell und das Cmdlet **Get-CsNetworkRegion** anzeigen. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. 

### <a name="to-view-network-region-information"></a>Zum Anzeigen von Informationen zur netzwerkregion

  - Anzeigen von Informationen zu all Ihre netzwerkregionen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
        Get-CsNetworkRegion
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Weitere Informationen finden Sie im Hilfethema zum [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) -Cmdlet.


## <a name="create-or-modify-network-regions"></a>Erstellen oder Ändern von netzwerkregionen 

Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche. Jeder netzwerkregion muss mit einem zentralen Standort zugeordnet werden. Am zentrale Standort ist der Data Center-Website auf dem Call Admission Control (, CAC)-bandbreitenrichtliniendienst ausgeführt wird. Die Skype Business Server-Systemsteuerung können Sie netzwerkregionen konfigurieren. Netzwerkregionen umfassen Einstellungen, die bestimmen, ob alternative Pfade über das Internet für Audio- und videoverbindungen zulässig sind. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregion. Verwenden Sie dieses Thema zum Erstellen und Ändern von netzwerkregionen. 

### <a name="to-create-a-network-region"></a>So erstellen Sie eine netzwerkregion

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf **neu**.

5.  Geben Sie auf der Seite **Neue Region** einen Wert in das Feld **Name** ein. Dieser Wert muss innerhalb Ihrer Skype für Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie aus der Dropdownliste **zentraler Standort** den zentralen Standort für diese netzwerkregion aus.

7.  Das Kontrollkästchen **Aktivieren audio alternativen Pfad** ist standardmäßig aktiviert. Dieses Feld bestimmt, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite vorhanden ist. Deaktivieren Sie dieses Kontrollkästchen, wenn Sie die Verschiebung an das Internet deaktivieren müssen. Wenn Ihre Anrufe Anrufe über das Internet ist, muss dieses Kontrollkästchen aktiviert, unabhängig von den bandbreiteneinstellungen.

8.  Das Kontrollkästchen **Aktivieren video alternativen Pfad** ist standardmäßig aktiviert. Dieses Feld bestimmt, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite vorhanden ist. Deaktivieren Sie dieses Kontrollkästchen, wenn Sie die Verschiebung an das Internet deaktivieren müssen. Wenn Ihre Anrufe Anrufe über das Internet ist, muss dieses Kontrollkästchen aktiviert, unabhängig von den bandbreiteneinstellungen.

9.  (Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu dieser Region bereitzustellen, die durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit ausführen**.

Die **zugeordnete Sites** -Tabelle wird nicht für die Erstellung einer netzwerkregion verwendet. Ordnen Sie eine Website einen Bereich beim Erstellen oder ändern die Website. Weitere Informationen hierzu finden Sie unter [Verwalten der anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>So ändern Sie eine netzwerkregion

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Klicken Sie auf der Seite **Region bearbeiten** können Sie die Einstellungen ändern, zum Aktivieren und Deaktivieren von Audio und Video alternative Pfade, und ändern Sie die Beschreibung (Informationen hierzu finden Sie im Abschnitt "So erstellen eine netzwerkregion" weiter oben in diesem Thema.

7.  Klicken Sie auf **Commit ausführen**.

Die **zugeordnete Websites** auf dieser Seite können nicht geändert werden. Die Liste der zugehörigen Websites ist für Verweis bereitgestellt, sodass Sie welche Websites betroffen sind kennen, wenn Sie die regionseinstellungen ändern.


## <a name="delete-existing-network-regions"></a>Löschen von vorhandenen netzwerkregionen 

Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche. Jeder netzwerkregion muss mit einem zentralen Standort zugeordnet werden. Am zentrale Standort ist der Data Center-Website auf dem Call Admission Control (, CAC)-bandbreitenrichtliniendienst ausgeführt wird. Die Skype Business Server-Systemsteuerung können Sie netzwerkregionen konfigurieren. Netzwerkregionen umfassen Einstellungen, die bestimmen, ob alternative Pfade über das Internet für Audio- und videoverbindungen zulässig sind. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregion. Verwenden Sie in diesem Thema, um vorhandene netzwerkregionen zu löschen. 

### <a name="to-delete-a-network-region"></a>So löschen Sie eine netzwerkregion

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, den, die Sie löschen möchten.
  
    > [!NOTE]  
    > Sie können mehrere Regionen zu einem Zeitpunkt löschen. Zu diesem Zweck, drücken Sie STRG, und wählen Sie mehrere Regionen aus, während Sie die STRG-Taste gedrückt halten. Oder, um alle Bereiche ausgewählt haben, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.


    > [!WARNING]  
    > Eine netzwerkregion kann nicht entfernt werden, wenn sie einen Netzwerkstandort zugeordnet ist. Wenn Sie versuchen, einen Bereich einer Website zugeordnet zu entfernen, erhalten Sie eine Fehlermeldung angezeigt. Um herauszufinden, ob ein Bereich alle Websites zugeordnet ist, wählen Sie die Region, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .


## <a name="see-also"></a>Siehe auch

[Verwalten von netzwerkregionsrouten](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
