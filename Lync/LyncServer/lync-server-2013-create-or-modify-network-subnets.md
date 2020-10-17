---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerk Subnetzen'
description: 'Lync Server 2013: Netzwerk-Subnetze erstellen oder ändern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546921"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Erstellen oder Ändern von Netzwerk-Subnetzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Ein Netzwerksubnetz muss einem Netzwerkstandort zugeordnet sein, damit der geografische Standort und der zu diesem Subnetz gehörende Host ermittelt werden können. Sie können lync Server-Systemsteuerung zum Konfigurieren von Subnetzen verwenden. Im lync Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen. Ausführliche Informationen zum Löschen von Netzwerk Subnetzen finden Sie unter [Löschen von Netzwerksubnetzen in lync Server 2013](lync-server-2013-deleting-network-subnets.md).

In den meisten Bereitstellungen von Microsoft lync Server 2013, in denen die Anrufsteuerung (Call Admission Control, CAC) implementiert ist, wird in der Regel eine große Anzahl von Subnetzen vorhanden sein. Aus diesem Grund ist es häufig am besten, Subnetze aus dem lync Server-Verwaltungsshell zu konfigurieren. Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Cmdlet **Import-CSV**von Windows PowerShell aufrufen. Wenn Sie diese beiden Cmdlets zusammen verwenden, können Sie die Subnetzeinstellungen aus einer durch Trennzeichen getrennten Datei (Comma-Separated Values, CSV) abrufen und mehrere Subnetze gleichzeitig erstellen. Beispiele für die Erstellung von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>So erstellen Sie ein Netzwerksubnetz

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf **Neu**.

5.  Geben Sie unter **Neues Subnetz** einen Wert im Feld **Subnetz-ID** ein. Dabei muss es sich um eine IP-Adresse (z. B. 174.11.12.0) und um die erste Adresse im IP-Adressbereich handeln, der vom Subnetz definiert wurde.

6.  Geben Sie im Feld **Maske** einen numerischen Wert von 1 bis 32 ein.
    
    <div>
    

    > [!NOTE]  
    > Dieser Wert stellt die Bitmaske dar, die auf das erstellte Subnetz angewendet werden soll.

    
    </div>

7.  Wählen Sie in **Netzwerkstandort-ID** den Standort aus, zu dem dieses Subnetz gehört.

8.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Subnetz ein, die nicht durch den Namen allein vermittelt werden können.

9.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>So ändern Sie ein Netzwerksubnetz

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite **Subnetz bearbeiten** können Sie die Bitmaske, den zugeordneten Netzwerkstandort oder die Beschreibung ändern. Beachten Sie beim Ändern der Bitmaske, dass die Subnetz-ID noch immer der ersten Adresse in dem vom Subnetz definierten IP-Adressbereich entsprechen muss.

7.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen von Netzwerk Subnetzen in lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[Informationen zu netzwerkregionen, Standorten und Subnetzen in lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Gruppe-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

