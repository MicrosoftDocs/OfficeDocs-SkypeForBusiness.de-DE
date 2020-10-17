---
title: 'Lync Server 2013: Erstellen von Netzwerk Regions Links'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e8c3d0fd254ba780b91d554402ca38d30f7073
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515562"
---
# <a name="create-network-region-links-in-lync-server-2013"></a>Erstellen von Netzwerk Regions Links in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Regionen in einem Netzwerk sind über eine physische WAN-Verbindung verbunden. Eine *Netzwerk Regions Verbindung* erstellt eine Verknüpfung zwischen zwei Regionen, die für die Anrufsteuerung konfiguriert sind, und legt die Bandbreitenbeschränkungen für den Audio-und Videodatenverkehr zwischen diesen Regionen fest.

Ausführliche Informationen zum Arbeiten mit Netzwerk Regions Verknüpfungen finden Sie in der lync Server-Verwaltungsshell Dokumentation zu den folgenden Cmdlets:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Gruppe-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

Die Beispieltopologie hat eine Verbindung zwischen den Regionen Nordamerika und APAC sowie eine Verbindung zwischen den Regionen EMEA und APAC. Jede dieser Regions Verknüpfungen wird durch die WAN-Bandbreite eingeschränkt, wie in der Tabelle "Bereichs Link-bandbreiteninformationen" im [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) Abschnitt der Planungsdokumentation beschrieben.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>So erstellen Sie Netzwerk Regions Verknüpfungen mithilfe von lync Server-Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das New-CsNetworkRegionLink-Cmdlet aus, um die Regions Verknüpfungen zu erstellen und entsprechende bandbreitenrichtlinienprofile anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>So erstellen Sie Netzwerk Regions Verknüpfungen mithilfe von lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Regions Verknüpfung** .

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **neue Regions Verknüpfung** auf **Name** , und geben Sie dann einen Namen für die Netzwerk Regions Verknüpfung ein.

6.  Klicken Sie auf **netzwerkregion \# 1**, und klicken Sie dann auf die netzwerkregion in der Liste, die Sie mit der netzwerkregion 2 verknüpfen möchten \# .

7.  Klicken Sie auf **netzwerkregion \# 2**, und klicken Sie dann auf eine netzwerkregion in der Liste, die Sie mit der netzwerkregion 1 verknüpfen möchten \# .

8.  Klicken Sie optional auf **bandbreitenrichtlinie**, und wählen Sie dann das bandbreitenrichtlinienprofil aus, das Sie auf den Link netzwerkregion anwenden möchten.
    
    <div class=" ">
    

    > [!NOTE]  
    > Wenden Sie nur dann eine bandbreitenrichtlinie an, wenn die Netzwerk Regions Verbindung Bandbreiteneinschränkungen unterliegt und Sie die Anrufsteuerung verwenden möchten, um den Mediendatenverkehr in dieser Verbindung zu steuern.

    
    </div>

9.  Klicken Sie auf **Commit ausführen**.

10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere Regionen, um die Erstellung von Netzwerk Regions Verknüpfungen für Ihre Topologie abzuschließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>
