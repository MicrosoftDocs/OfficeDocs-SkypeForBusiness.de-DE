---
title: Verwalten von Netzwerksubnetzen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In den meisten Bereitstellungen von Skype for Business Server, in denen die Anrufsteuerung implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es häufig am besten, Subnetze über die Skype for Business Server-Verwaltungsshell zu konfigurieren.
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816395"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Verwalten von Netzwerksubnetzen in Skype for Business Server

Sie können entweder die Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell zum Verwalten von Netzwerksubnetzen verwenden. In den meisten Bereitstellungen von Skype for Business Server, in denen die Anrufsteuerung implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es häufig am besten, Subnetze über die Skype for Business Server-Verwaltungsshell zu konfigurieren.

Verwenden Sie die Abschnitte in diesem Artikel zum Anzeigen von Netzwerksubnetzinformationen oder zum Erstellen, Ändern oder Löschen von Netzwerksubnetzen. 

## <a name="view-network-subnet-information"></a>Anzeigen von Netzwerksubnetzinformationen 

Mit dem folgenden Verfahren können Sie ein Netzwerksubnetz anzeigen. In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerksubnetz erstellen, ändern oder löschen. 

### <a name="to-view-a-network-subnet"></a>So zeigen Sie ein Netzwerksubnetz an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Subnetz".**

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.
 
    > [!NOTE]  
    > Sie können nur jeweils ein Subnetz anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Konfigurationsinformationen zu Netzwerksubnetzen mithilfe Windows PowerShell Cmdlets

Netzwerksubnetzinformationen können mithilfe des cmdlets Windows PowerShell und Get-CsNetworkSubnet angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>So zeigen Sie Netzwerksubnetzinformationen an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerksubnetzen den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkSubnet
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).


## <a name="create-or-modify-network-subnets"></a>Erstellen oder Ändern von Netzwerksubnetzen 

Ein Netzwerksubnetz muss einem Netzwerkstandort zugeordnet sein, damit der geografische Standort und der zu diesem Subnetz gehörende Host ermittelt werden können. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Subnetze zu konfigurieren. In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerksubnetz erstellen, ändern oder löschen. 

In den meisten Bereitstellungen von Skype for Business Server, in denen die Anrufsteuerung implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es häufig am besten, Subnetze über die Skype for Business Server-Verwaltungsshell zu konfigurieren. Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem cmdlet Windows PowerShell **Import-CSV aufrufen.** Wenn Sie diese beiden Cmdlets zusammen verwenden, können Sie die Subnetzeinstellungen aus einer durch Trennzeichen getrennten Datei (Comma-Separated Values, CSV) abrufen und mehrere Subnetze gleichzeitig erstellen. Beispiele für die Erstellung von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>So erstellen Sie ein Netzwerksubnetz

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Subnetz".**

4.  Klicken Sie auf der Seite **Subnetz** auf **Neu**.

5.  Geben Sie unter **Neues Subnetz** einen Wert im Feld **Subnetz-ID** ein. Dabei muss es sich um eine IP-Adresse (z. B. 174.11.12.0) und um die erste Adresse im IP-Adressbereich handeln, der vom Subnetz definiert wurde.

6.  Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.

    > [!NOTE]  
    > Dieser Wert stellt die Bitmaske dar, die auf das erstellte Subnetz angewendet werden soll.

7.  Wählen Sie in **Netzwerkstandort-ID** den Standort aus, zu dem dieses Subnetz gehört.

8.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Subnetz ein, die nicht durch den Namen allein vermittelt werden können.

9.  Klicken Sie auf **Commit**.


### <a name="to-modify-a-network-subnet"></a>So ändern Sie ein Netzwerksubnetz

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Subnetz".**

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite **Subnetz bearbeiten** können Sie die Bitmaske, den zugeordneten Netzwerkstandort oder die Beschreibung ändern. Beachten Sie beim Ändern der Bitmaske, dass die Subnetz-ID noch immer der ersten Adresse in dem vom Subnetz definierten IP-Adressbereich entsprechen muss.

7.  Klicken Sie auf **Commit**.

## <a name="delete-network-subnets"></a>Löschen von Netzwerksubnetzen

Mithilfe des folgenden Verfahrens können Sie ein Subnetz löschen. In der Skype for Business Server-Systemsteuerung können Sie ein Netzwerksubnetz erstellen, ändern oder löschen. 

In den meisten Bereitstellungen von Skype for Business Server, in denen die Anrufsteuerung implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es häufig am besten, Subnetze über die Skype for Business Server-Verwaltungsshell zu konfigurieren. Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem cmdlet Windows PowerShell **Import-CSV aufrufen.** Wenn Sie diese beiden Cmdlets zusammen verwenden, können Sie die Subnetzeinstellungen aus einer durch Trennzeichen getrennten Datei (Comma-Separated Values, CSV) abrufen und mehrere Subnetze gleichzeitig erstellen. Beispiele für die Erstellung von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>So löschen Sie ein Netzwerksubnetz

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Subnetz".**

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.
 
    > [!NOTE]  
    > Sie können mehrere Subnetze in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Subnetze aus. Wenn Sie alle Subnetze auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**.

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.


## <a name="see-also"></a>Siehe auch

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
