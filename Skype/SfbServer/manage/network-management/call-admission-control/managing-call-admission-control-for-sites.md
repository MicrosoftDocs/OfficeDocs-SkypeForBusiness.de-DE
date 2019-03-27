---
title: Verwalten der anrufsteuerung für Standorte
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Netzwerkstandorte sind die Büros oder Speicherorte innerhalb jeder netzwerkregion der anrufsteuerung (CAC), E9-1-1 und Media Bypass Bereitstellungen aufrufen.
ms.openlocfilehash: 53140cf03110991f2c757e5d52e30a6c7db1d7de
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895419"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Verwalten der Anrufsteuerung für Standorte in Skype for Business Server

Netzwerkstandorte sind die Büros oder Speicherorte innerhalb jeder netzwerkregion der anrufsteuerung (CAC), E9-1-1 und Media Bypass Bereitstellungen aufrufen. Verwenden Sie die Verfahren in diesem Artikel, um die anrufsteuerung bei den Netzwerkstandorten konfigurieren.

## <a name="configure-network-site-links"></a>Konfigurieren von netzwerkstandortverknüpfungen

Innerhalb einer Call Admission Control (, CAC) Konfiguration können Sie Netzwerk an standortübergreifende Richtlinien erstellen, die bandbreiteneinschränkungen zwischen Standorten definieren, die direkt verbunden sind. Wenn Netzwerkstandorten eine direkte Verknüpfung freigeben, können die Bandbreite für Audio- und videoverbindungen zwischen zwei Websites definiert werden. Sie können die Skype Business Server-Systemsteuerung Website Netzwerkrichtlinien konfigurieren, dazu können nur mithilfe der Skype-Cmdlets für Business Server-Verwaltungsshell. Sie können erstellen, ändern und entfernen eine netzwerkstandortverknüpfung (auch bekannt als eine standortübergreifende Netzwerkrichtlinie) aus der Skype für Business Server-Verwaltungsshell.

### <a name="to-create-a-network-site-link"></a>Erstellen Sie eine netzwerkstandortverknüpfung

1.  Melden Sie sich bei dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist, an.

2.  Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

3.  Geben Sie über die Befehlszeile den folgenden Befehl ein, ersetzen die gültigen Werte für die Konfiguration aus:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Dieses Beispiel erstellt eine neue netzwerkstandortverknüpfung mit dem Namen Reno\_Portland, die bandbreiteneinschränkungen zwischen Reno und Portland Netzwerkstandorte festlegt. Netzwerkstandorte und das bandbreitenrichtlinienprofil müssen vor dem Ausführen dieses Befehls bereits vorhanden.

Ausführliche Beschreibung der Parameter finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Um eine Liste der bandbreitenrichtlinienprofile abzurufen, die auf die netzwerkstandortverknüpfung angewendet werden können, rufen Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Weitere Informationen hierzu finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>So ändern Sie eine netzwerkstandortverknüpfung

1.  Melden Sie sich bei dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist, an.

2.  Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Set-CsNetworkInterSitePolicy** , um die Eigenschaften einer bestimmten netzwerkstandortverknüpfung ändern. Sie können einen (oder beide) ändern oder die verbundenen Websites, und Sie können das bandbreitenrichtlinienprofil, das dem Hyperlink zugeordnete ändern. Nachfolgend finden Sie ein Beispiel zum Ändern einer Website Verknüpfung mit dem Namen "Reno" mithilfe des bandbreitenrichtlinienprofil\_Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Ausführliche Beschreibung der Parameter finden Sie unter [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>So löschen Sie eine netzwerkstandortverknüpfung

1.  Melden Sie sich bei dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist, an.

2.  Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy** , um eine netzwerkstandortverknüpfung zu entfernen. Das folgende Beispiel löscht die Reno\_Portland netzwerkstandortverknüpfung:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Ausführliche Beschreibung der Parameter finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Anzeigen von Informationen zu Netzwerkstandorten

Netzwerkstandorte sind die Niederlassungen oder Standorte innerhalb jeder Region einer anrufsteuerung (CAC) oder Enhanced 9-1-1-Bereitstellung konfiguriert sind. Sie können Informationen zu Netzwerkstandorten in entweder die Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell anzeigen. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Zum Anzeigen von Informationen zu Netzwerkstandorten in Skype Business Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf der Website, die Sie anzeigen möchten.
 
    > [!NOTE]  
    > Sie können nur Informationen für einen Standort zu einem Zeitpunkt anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zu Netzwerkstandorten mithilfe von Windows PowerShell-cmdlets

Sie können Informationen zu Netzwerkstandorten mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkSite anzeigen. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

### <a name="to-view-network-site-information"></a>So zeigen Sie netzwerkstandortinformationen an

  - Anzeigen von Informationen zu allen Netzwerkstandorten, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
        Get-CsNetworkSite
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Erstellen oder Ändern von Netzwerkstandorten 

Netzwerkstandorte sind die Niederlassungen oder Standorte innerhalb jeder Region einer anrufsteuerung (CAC) oder Enhanced 9-1-1-Bereitstellung konfiguriert sind. Die Skype Business Server-Systemsteuerung können zum Konfigurieren von Websites und Regionen zuzuordnen. Beispielsweise könnte eine netzwerkregion für Nordamerika Netzwerke Websites wie "Chicago" und "Redmond" Vancouver zugeordnet werden. Ein Netzwerkstandort CAC muss für jede Website innerhalb einer Organisation erstellt werden, auch wenn diese Website keine Netzwerkbandbreite ist eingeschränkt wurde. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern und Löschen von Netzwerk-Sites. Verwenden Sie die folgenden Verfahren zum Erstellen oder Ändern eines Netzwerkstandorts. 

### <a name="to-create-a-network-site"></a>So erstellen Sie einen Netzwerkstandort

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf **neu**.

5.  Geben Sie unter **Neue Website**einen Namen für diese Website in das Feld **Name** ein.

    > [!NOTE]  
    > Standortnamen müssen innerhalb der Skype für Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Region** eine netzwerkregion an diesem Standort zugeordnet.

7.  (Optional) Wenn Sie die Netzwerkbandbreite ist eingeschränkt auf Audio- oder Videoinhalten Anrufe an diese Website platzieren möchten, wählen Sie das bandbreitenrichtlinienprofil mit den entsprechenden Einstellungen aus der Dropdownliste **bandbreitenrichtlinie** aus.
 
    > [!NOTE]  
    > Sie können die Details zu den verfügbaren bandbreitenrichtlinienprofile anzeigen oder erstellen ein neues bandbreitenrichtlinienprofil auf der Seite **Richtlinie Profil** , der die Gruppe **Netzwerkkonfiguration** . Weitere Informationen hierzu finden Sie unter [Verwalten von Netzwerk-bandbreitenrichtlinienprofilen](managing-network-bandwidth-policy-profiles.md).

8.  (Optional) Wenn Sie ortungseinstellungen für diese Website bereitstellen möchten, wählen Sie aus der Dropdownliste **ortungsrichtlinie** eine ortungsrichtlinie aus.

    > [!NOTE]  
    > Die Standortrichtlinie weist bestimmte erweiterte E9-1-1 (E9-1-1) und Client standorteinstellungen zu der Website. Sie können die Details zu den verfügbaren Standortrichtlinien anzeigen oder erstellen eine neue ortungsrichtlinie auf der Seite **Standortrichtlinie** die Gruppe **Netzwerkkonfiguration** . 

9.  (Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu dieser Website bereitzustellen, die durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit ausführen**.

    > [!NOTE]  
    > Sie verwenden die **Subnetze verknüpften** Tabelle nicht, wenn Sie einen neuen Netzwerkstandort erstellen. Sie Zuordnen eines Subnetzes zu einer Website, wenn Sie erstellen oder ändern das Subnetz. Weitere Informationen hierzu finden Sie unter [Verwalten von Netzwerksubnetzen](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>So ändern Sie einen Netzwerkstandort

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf der Website, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Klicken Sie auf der Seite **Standort bearbeiten** können Sie die Beschreibung, Region, bandbreitenrichtlinienprofil und ortungsrichtlinie, die der Website zugeordnet ändern. Weitere Informationen hierzu finden Sie unter [So erstellen Sie einen Netzwerkstandort](#to-create-a-network-site) oben.

7.  Klicken Sie auf **Commit ausführen**.

Die Tabelle **Zugeordnete Subnetze** auf dieser Seite können nicht geändert werden. Die Liste der zugeordnete Subnetze zu Referenzzwecken bereitgestellt, sodass welche Subnetze betroffen sind, wenn Sie die Einstellungen ändern bekannt sind.


## <a name="delete-an-existing-network-site"></a>Löschen Sie einen vorhandenen Netzwerkstandort

Netzwerkstandorte sind die Niederlassungen oder Standorte innerhalb jeder Region einer anrufsteuerung (CAC) oder Enhanced 9-1-1-Bereitstellung konfiguriert sind. Die Skype Business Server-Systemsteuerung können zum Konfigurieren von Websites und Regionen zuzuordnen. Beispielsweise könnte eine netzwerkregion für Nordamerika Netzwerke Websites wie "Chicago" und "Redmond" Vancouver zugeordnet werden. Ein Netzwerkstandort CAC muss für jede Website innerhalb einer Organisation erstellt werden, auch wenn diese Website keine Netzwerkbandbreite ist eingeschränkt wurde. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern und Löschen von Netzwerk-Sites. Verwenden Sie das folgende Verfahren, um einen vorhandenen Netzwerkstandort zu löschen. Ausführliche Informationen zum Erstellen oder Ändern von Netzwerkstandorten finden Sie unter [Verwalten der anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>So löschen Sie einen Netzwerkstandort

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf der Website, die Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehrere Websites zu einem Zeitpunkt löschen. Zu diesem Zweck STRG-Taste gedrückt, und wählen Sie mehrere Standorte während Sie die STRG-Taste gedrückt halten. Oder, um alle Websites auszuwählen, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    

    > [!WARNING]  
    > Sie können einen Netzwerkstandort nicht entfernen, wenn sie ein Netzwerksubnetz zugeordnet ist. Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine Website, die ein Subnetz zugeordnet zu entfernen. Um herauszufinden, ob eine Website Subnetze zugeordnet ist, klicken Sie auf der Website, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .


## <a name="see-also"></a>Siehe auch


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
