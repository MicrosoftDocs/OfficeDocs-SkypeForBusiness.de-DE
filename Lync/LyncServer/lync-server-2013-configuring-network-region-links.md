---
title: 'Lync Server 2013: Konfigurieren von Netzwerk Regions Verknüpfungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895c85a80d3e5a7fadee3dccad25f9d89f04028a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Konfigurieren von Netzwerkbereichs Links in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren. Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden. Sie können die lync Server-Systemsteuerung verwenden, um eine Verknüpfung zwischen zwei netzwerkregionen zu definieren und die Bandbreiteneinschränkungen für Audio-und Videoverbindungen zwischen diesen Regionen festzulegen. Details zum Löschen einer vorhandenen Netzwerk Regions Verknüpfung finden Sie unter [Löschen von Netzwerkbereichs Links in lync Server 2013](lync-server-2013-deleting-network-region-links.md).

<div>

## <a name="to-create-a-network-region-link"></a>So erstellen Sie eine Netzwerk Regions Verknüpfung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Link**.

4.  Klicken Sie auf der Seite **Regions Link** auf **neu**.

5.  Geben Sie im Feld **neuer Bereich**einen Wert in das Feld **Name** ein.
    
    <div>
    

    > [!NOTE]  
    > Dieser Wert muss innerhalb ihrer lync Server 2013-Bereitstellung eindeutig sein.

    
    </div>

6.  Wählen Sie in der Dropdownliste **netzwerkregion \#1** einen der beiden zu verknüpfende Regionen aus.

7.  Wählen Sie in der Dropdownliste **netzwerkregion \#2** die andere Region aus, die verknüpft werden soll. Diese Region muss sich von der für netzwerkregion \#1 ausgewählten Region unterscheiden.

8.  Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe zwischen diesen Regionen festlegen möchten, wählen Sie in der Dropdownliste **bandbreitenrichtlinie** ein Profil für Bandbreitenrichtlinien aus.

9.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>So ändern Sie eine Netzwerk Regions Verknüpfung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Link**.

4.  Klicken Sie auf der Seite **Regions Link** auf den zu ändernden Bereichs Link.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Im **Link "Region bearbeiten**" können Sie die verknüpften Regionen oder das bandbreitenrichtlinienprofil für diesen Link ändern.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen von Netzwerkbereichs Links in lync Server 2013](lync-server-2013-deleting-network-region-links.md)  


[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
