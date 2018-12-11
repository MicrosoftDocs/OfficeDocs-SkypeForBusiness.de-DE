---
title: Verwalten von Netzwerksubnetzen
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen. Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.
ms.openlocfilehash: e855805aebc61228c185d04cba1faa9de6700f84
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223353"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Verwalten von Netzwerksubnetzen in Skype für Business Server

Sie können entweder die Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell verwenden, zum Verwalten von Netzwerksubnetzen. In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen. Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren.

Verwenden Sie in den Abschnitten in diesem Artikel, um Informationen zum Netzwerksubnetz anzuzeigen oder zu erstellen, ändern oder Löschen von Netzwerksubnetzen. 

## <a name="view-network-subnet-information"></a>Anzeigen von netzwerksubnetzinformationen 

Das folgende Verfahren können Sie ein Netzwerksubnetz anzeigen. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz. 

### <a name="to-view-a-network-subnet"></a>So zeigen Sie ein Netzwerksubnetz an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.
 
    > [!NOTE]  
    > Sie können nur jeweils ein Subnetz anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Zeigen Sie Netzwerksubnetz-Konfigurationsinformationen an, indem Sie mithilfe von Windows PowerShell-cmdlets

Informationen zum Netzwerksubnetz kann mithilfe von Windows PowerShell und das Cmdlet "Get-CsNetworkSubnet" angezeigt werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

### <a name="to-view-network-subnet-information"></a>So zeigen Sie Informationen zum Netzwerksubnetz an

  - Um Informationen über alle netzwerksubnetze anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkSubnet
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Erstellen oder Ändern von Netzwerksubnetzen 

Ein Netzwerksubnetz muss für die Bestimmung des geografischen Standorts des Hosts, gehören zu diesem Subnetz einem Netzwerkstandort zugeordnet werden. Die Skype Business Server-Systemsteuerung können Sie Subnetze konfigurieren. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz. 

In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen. Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren. Dort können Sie **New-CsNetworkSubnet** in Verbindung mit der Windows PowerShell-Cmdlet **Import-CSV**aufrufen. Diese Cmdlets zusammen verwenden, können Sie in Subnetz Einstellungen aus einer Datei durch Kommas getrennten Werten (CSV) lesen und Erstellen von mehreren Subnetzen zur selben Zeit. Beispiele dafür, wie Sie zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-csnetworksubnet aus](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Erstellen Sie ein Netzwerksubnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf **neu**.

5.  Geben Sie in **Neues Subnetz**einen Wert im Feld **Subnetz-ID** ein. Dies muss eine IP-Adresse (beispielsweise 174.11.12.0), und es muss die erste Adresse in der IP-Adressbereich durch das Subnetz definiert sein.

6.  Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.

    > [!NOTE]  
    > Dieser Wert ist die Bitmaske dar, auf das erstellte Subnetz angewendet werden soll.

7.  Wählen Sie in **Netzwerkstandort-ID**, zu der dieses Subnetz gehört.

8.  (Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu diesem Subnetz bereitzustellen, die durch den Namen allein vermittelt werden können.

9.  Klicken Sie auf **Commit ausführen**.


### <a name="to-modify-a-network-subnet"></a>So ändern Sie ein Netzwerksubnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite **Subnetz bearbeiten** können Sie die Bitmaske, die zugeordneten Netzwerkstandort oder die Beschreibung ändern. Wenn Sie die Bitmaske ändern, Überwachungsfunktionen Sie berücksichtigen, die der Subnetz-ID weiterhin die erste Adresse in der IP-Adressbereich durch das Subnetz definiert sein muss.

7.  Klicken Sie auf **Commit ausführen**.

## <a name="delete-network-subnets"></a>Löschen von Netzwerksubnetzen

Das folgende Verfahren können Sie um ein Subnetz zu löschen. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen ein Netzwerksubnetz. 

In den meisten Bereitstellungen von Skype für Business Server, auf dem die anrufsteuerung (CAC) implementiert wird, in der Regel wird eine große Anzahl von Subnetzen. Aus diesem Grund ist es oft sollten Sie Subnetze aus der Skype für Business Server-Verwaltungsshell zu konfigurieren. Dort können Sie **New-CsNetworkSubnet** in Verbindung mit der Windows PowerShell-Cmdlet **Import-CSV**aufrufen. Diese Cmdlets zusammen verwenden, können Sie in Subnetz Einstellungen aus einer Datei durch Kommas getrennten Werten (CSV) lesen und Erstellen von mehreren Subnetzen zur selben Zeit. Beispiele dafür, wie Sie zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-csnetworksubnet aus](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>So löschen Sie ein Netzwerksubnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.
 
    > [!NOTE]  
    > Sie können mehrere Subnetze zu einem Zeitpunkt löschen. Zu diesem Zweck, drücken Sie STRG, und wählen Sie mehrere Subnetze, während Sie die STRG-Taste gedrückt halten. Oder, wenn alle Subnetze auswählen möchten, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie anschließend auf **OK**.


## <a name="see-also"></a>Siehe auch

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  