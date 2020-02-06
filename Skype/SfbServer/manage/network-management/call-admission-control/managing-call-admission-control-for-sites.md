---
title: Verwalten der Anrufsteuerung für Websites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Netzwerk Websites sind die Büros oder Standorte innerhalb der einzelnen netzwerkregionen der Anruf Zulassungs Steuerung (CAC), E9-1-1 und Media Bypass-Bereitstellungen.
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817514"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Verwalten der Anrufsteuerung für Standorte in Skype for Business Server

Netzwerk Websites sind die Büros oder Standorte innerhalb der einzelnen netzwerkregionen der Anruf Zulassungs Steuerung (CAC), E9-1-1 und Media Bypass-Bereitstellungen. Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um die Anrufsteuerung für Netzwerk Websites zu konfigurieren.

## <a name="configure-network-site-links"></a>Konfigurieren von Netzwerkstandort Links

Innerhalb einer Anruf Steuerungskonfiguration können Sie netzwerkübergreifende Richtlinien erstellen, die Bandbreiteneinschränkungen zwischen Websites definieren, die direkt verknüpft sind. Wenn Netzwerk Websites einen direkten Link verwenden, können Bandbreiteneinschränkungen für Audio-und Videoverbindungen zwischen diesen beiden Websites definiert werden. Sie können die Skype for Business Server-Systemsteuerung nicht zum Konfigurieren von Netzwerk Website Richtlinien verwenden, dies kann nur mithilfe von Cmdlets aus der Skype for Business Server-Verwaltungsshell erfolgen. Über die Skype for Business Server-Verwaltungsshell können Sie einen Link zur Netzwerk Website (auch bekannt als netzwerkübergreifende Website Richtlinie) erstellen, ändern und entfernen.

### <a name="to-create-a-network-site-link"></a>So erstellen Sie einen Netzwerkstandort Link

1.  Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist.

2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.

3.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und ersetzen Sie Werte, die für Ihre Konfiguration gültig sind:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    In diesem Beispiel wird eine neue netzwerkstandortverknüpfung namens\_Reno Portland erstellt, die Bandbreiteneinschränkungen zwischen den Netzwerkstandorten Reno und Portland festlegt. Die Netzwerk Websites und das bandbreitenrichtlinienprofil müssen bereits vorhanden sein, bevor Sie diesen Befehl ausführen.

Ausführliche Beschreibungen zu Parametern finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Rufen Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile** auf, um eine Liste der bandbreitenrichtlinienprofile abzurufen, die auf den Link Netzwerk Website angewendet werden können. Ausführliche Informationen finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>So ändern Sie einen Link für eine Netzwerk Website

1.  Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist.

2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet " **Satz-CsNetworkInterSitePolicy** ", um die Eigenschaften einer bestimmten netzwerkstandortverknüpfung zu ändern. Sie können entweder (oder beide) oder die verbundenen Websites ändern, und Sie können das dem Link zugeordnete bandbreitenrichtlinienprofil ändern. Nachfolgend finden Sie ein Beispiel für das Ändern des bandbreitenrichtlinienprofils einer Standort\_Verknüpfung mit dem Namen Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Ausführliche Beschreibungen zu Parametern finden Sie unter [Satz-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>So löschen Sie einen Netzwerkstandort Link

1.  Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist.

2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy** , um einen Netzwerkstandort Link zu entfernen. Im folgenden Beispiel wird der Link\_zur Portland-Netzwerk Website von Reno gelöscht:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Ausführliche Beschreibungen der Parameter finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Anzeigen von Netzwerk Website Informationen

Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind. Sie können Informationen zur Netzwerk Website entweder in der Skype for Business Server-Systemsteuerung oder in der Skype for Business Server-Verwaltungsshell anzeigen. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>So zeigen Sie Netzwerk Website Informationen in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie anzeigen möchten.
 
    > [!NOTE]  
    > Sie können nur Informationen für eine Website gleichzeitig anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerk Website Informationen mithilfe von Windows PowerShell-Cmdlets

Sie können Netzwerk Website Informationen mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkSite anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

### <a name="to-view-network-site-information"></a>So zeigen Sie Netzwerk Website Informationen an

  - Wenn Sie Informationen zu allen Ihren Netzwerk Websites anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkSite
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Erstellen oder Ändern von Netzwerk Websites 

Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen. Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein. Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist. Über das Skype for Business Server Control Panel können Sie Netzwerk Websites erstellen, ändern und löschen. Gehen Sie wie folgt vor, um eine Netzwerk Website zu erstellen oder zu ändern. 

### <a name="to-create-a-network-site"></a>So erstellen Sie eine Netzwerk Website

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf **neu**.

5.  Geben Sie auf der **neuen Website**im Feld **Name** einen Namen für diese Website ein.

    > [!NOTE]  
    > Websitenamen müssen innerhalb der Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Region** einen Netzwerkbereich aus, der dieser Website zugeordnet werden soll.

7.  Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe an diese Website vornehmen möchten, wählen Sie das bandbreitenrichtlinienprofil mit den entsprechenden Einstellungen in der Dropdownliste **bandbreitenrichtlinie** aus.
 
    > [!NOTE]  
    > Sie können die Details der verfügbaren bandbreitenrichtlinienprofile anzeigen oder ein neues bandbreitenrichtlinienprofil auf der Seite **Richtlinienprofil** der Gruppe **Netzwerkkonfiguration** erstellen. Ausführliche Informationen finden Sie unter [Verwalten von Netzwerkbandbreite-Richtlinienprofilen](managing-network-bandwidth-policy-profiles.md).

8.  Optional Wenn Sie die Standorteinstellungen für diese Website angeben möchten, wählen Sie in der Dropdownliste **Standortrichtlinie** eine Standortrichtlinie aus.

    > [!NOTE]  
    > Die Standortrichtlinie weist der Website bestimmte erweiterte 9-1-1-Einstellungen (E9-1-1) und Clientstandort Einstellungen zu. Sie können die Details der verfügbaren Standortrichtlinien anzeigen oder eine neue Standortrichtlinie erstellen, die sich auf der Seite " **Standortrichtlinie** " der Gruppe " **Netzwerkkonfiguration** " befindet. 

9.  Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu dieser Website bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.

10. Klicken Sie auf **Commit ausführen**.

    > [!NOTE]  
    > Wenn Sie eine neue Netzwerk Website erstellen, verwenden Sie die Tabelle **zugeordnete Subnetze** nicht. Sie verknüpfen ein Subnetz mit einer Website, wenn Sie das Subnetz erstellen oder ändern. Ausführliche Informationen finden Sie unter [Verwalten von Netzwerk-Subnetzen](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>So ändern Sie eine Netzwerk Website

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite " **Website bearbeiten** " können Sie die Beschreibung, die Region, das bandbreitenrichtlinienprofil und die der Website zugeordnete Standortrichtlinie ändern. Ausführliche Informationen finden Sie unter [So erstellen Sie eine Netzwerk Website](#to-create-a-network-site) oben.

7.  Klicken Sie auf **Commit ausführen**.

Auf dieser Seite können Sie die Tabelle **zugeordnete Subnets** nicht ändern. Die Liste der zugeordneten Subnetze wird als Referenz bereitgestellt, damit Sie wissen, welche Subnetze betroffen sind, wenn Sie die Websiteeinstellungen ändern.


## <a name="delete-an-existing-network-site"></a>Löschen einer vorhandenen Netzwerk Website

Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen. Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein. Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist. Über das Skype for Business Server Control Panel können Sie Netzwerk Websites erstellen, ändern und löschen. Gehen Sie wie folgt vor, um eine vorhandene Netzwerk Website zu löschen. Details zum Erstellen oder Ändern von Netzwerk Websites finden Sie unter [Verwalten der Anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>So löschen Sie eine Netzwerk Website

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehr als eine Website gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Websites aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Websites auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    

    > [!WARNING]  
    > Sie können eine Netzwerk Website nicht entfernen, wenn Sie einem Netzwerk-Subnetz zugeordnet ist. Wenn Sie versuchen, eine Website zu entfernen, die einem Subnetz zugeordnet ist, wird eine Fehlermeldung angezeigt. Wenn Sie feststellen möchten, ob eine Website mit Subnetzen verknüpft ist, klicken Sie auf die Website, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .


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
