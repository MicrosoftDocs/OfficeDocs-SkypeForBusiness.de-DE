---
title: Verwalten von Netzwerk-Subnetzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren.
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279480"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Verwalten von Netzwerksubnetzen in Skype for Business Server

Sie können die Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden, um Netzwerk-Subnets zu verwalten. In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren.

Verwenden Sie die Abschnitte in diesem Artikel, um Netzwerk-Subnetinformationen anzuzeigen oder Netzwerk-Subnets zu erstellen, zu ändern oder zu löschen. 

## <a name="view-network-subnet-information"></a>Netzwerk-Subnetz-Informationen anzeigen 

Sie können das folgende Verfahren verwenden, um ein Netzwerk-Subnetz anzuzeigen. In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen. 

### <a name="to-view-a-network-subnet"></a>So zeigen Sie ein Netzwerk-Subnetz an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.
 
    > [!NOTE]  
    > Sie können jeweils nur ein Subnetz anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerk-Subnet-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets

Netzwerk-Subnetz-Informationen können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkSubnet angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

### <a name="to-view-network-subnet-information"></a>So zeigen Sie Netzwerk-Subnetz-Informationen an

  - Wenn Sie Informationen zu allen Netzwerk-Subnetzen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkSubnet
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Erstellen oder Ändern von Netzwerk-Subnetzen 

Ein Netzwerk-Subnetz muss einer Netzwerk Website zugeordnet sein, um den geografischen Standort des Hosts zu ermitteln, der zu diesem Subnetz gehört. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Subnets zu konfigurieren. In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen. 

In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren. Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Windows PowerShell **-Cmdlet Import-CSV**aufrufen. Wenn Sie diese Cmdlets zusammen verwenden, können Sie die subneteinstellungen aus einer CSV-Datei (Comma-Separated Values) lesen und gleichzeitig mehrere Subnetze erstellen. Beispiele zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>So erstellen Sie ein Netzwerk-Subnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf **neu**.

5.  Geben Sie im **neuen Subnetz**einen Wert in das Feld **Subnet-ID** ein. Hierbei muss es sich um eine IP-Adresse (beispielsweise 174.11.12.0) handeln, die die erste Adresse im vom Subnetz definierten IP-Adressbereich sein muss.

6.  Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.

    > [!NOTE]  
    > Dieser Wert ist die Bitmaske, die auf das erstellte Subnetz angewendet werden soll.

7.  Wählen Sie unter **Netzwerk Website-ID**die Website aus, zu der dieses Subnetz gehört.

8.  Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu diesem Subnetz bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.

9.  Klicken Sie auf **Commit ausführen**.


### <a name="to-modify-a-network-subnet"></a>So ändern Sie ein Netzwerk-Subnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite " **Subnetz bearbeiten** " können Sie die Bitmaske, die zugeordnete Netzwerk Website oder die Beschreibung ändern. Beachten Sie beim Ändern der Bitmaske, dass die Subnetz-ID immer noch die erste Adresse im IP-Adressbereich sein muss, die vom Subnetz definiert ist.

7.  Klicken Sie auf **Commit ausführen**.

## <a name="delete-network-subnets"></a>Löschen von Netzwerk-Subnetzen

Sie können das folgende Verfahren verwenden, um ein Subnetz zu löschen. In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen. 

In den meisten Bereitstellungen von Skype for Business Server, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es am besten, Subnets aus der Skype for Business Server-Verwaltungsshell zu konfigurieren. Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Windows PowerShell **-Cmdlet Import-CSV**aufrufen. Wenn Sie diese Cmdlets zusammen verwenden, können Sie die subneteinstellungen aus einer CSV-Datei (Comma-Separated Values) lesen und gleichzeitig mehrere Subnetze erstellen. Beispiele zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>So löschen Sie ein Netzwerk-Subnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.
 
    > [!NOTE]  
    > Sie können mehr als ein Subnetz gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Subnetze aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Subnetze auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alles auswählen** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.


## <a name="see-also"></a>Siehe auch

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
