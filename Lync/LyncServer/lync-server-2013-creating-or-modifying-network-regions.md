---
title: 'Lync Server 2013: Erstellen oder Ändern von netzwerkregionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3ca5d44fd2278ffee8a3e9dd4494575cc64c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Erstellen oder Ändern von netzwerkregionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg. Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird. Sie können die lync Server-Systemsteuerung verwenden, um netzwerkregionen zu konfigurieren. Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der lync Server-Systemsteuerung können Sie einen Netzwerkbereich erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um netzwerkregionen zu erstellen und zu ändern. Details zum Löschen vorhandener netzwerkregionen finden Sie unter [Löschen vorhandener netzwerkregionen in lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>So erstellen Sie einen Netzwerkbereich

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf **neu**.

5.  Geben Sie auf der Seite **neuer Bereich** einen Wert in das Feld **Name** ein. Dieser Wert muss innerhalb Ihrer Microsoft lync Server 2013-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Central Site** die zentrale Website für diesen Netzwerkbereich aus.

7.  Das Kontrollkästchen audioalternativen **Pfad aktivieren** ist standardmäßig aktiviert. Dieses Feld bestimmt, ob Audioanrufe durch einen alternativen Pfad weitergeleitet werden, wenn im primären Pfad keine ausreichende Bandbreite vorhanden ist. Deaktivieren Sie dieses Kontrollkästchen nur, wenn Sie die Verschiebung zum Internet deaktivieren müssen. Wenn es sich bei ihren anrufen um Internet Anrufe handelt, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

8.  Das Kontrollkästchen **Video alternativen Pfad aktivieren** ist standardmäßig aktiviert. Dieses Feld bestimmt, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn im primären Pfad keine ausreichende Bandbreite vorhanden ist. Deaktivieren Sie dieses Kontrollkästchen nur, wenn Sie die Verschiebung zum Internet deaktivieren müssen. Wenn es sich bei ihren anrufen um Internet Anrufe handelt, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

9.  Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu dieser Region bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.

10. Klicken Sie auf **Commit ausführen**.

Die Tabelle **zugeordnete Websites** wird nicht zum Erstellen eines Netzwerkbereichs verwendet. Sie ordnen eine Website einem Bereich zu, wenn Sie die Website erstellen oder ändern. Ausführliche Informationen finden Sie unter [erstellen oder Ändern von Netzwerk Websites in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>So ändern Sie einen Netzwerkbereich

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf den Bereich, den Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite " **Bereich bearbeiten** " können Sie die Einstellungen für die Aktivierung und Deaktivierung von Audio-und Video Alternativen Pfaden ändern und die Beschreibung ändern (Einzelheiten finden Sie im Abschnitt "So erstellen Sie einen Netzwerkbereich" weiter oben in diesem Thema.

7.  Klicken Sie auf **Commit ausführen**.

Auf dieser Seite können Sie die **zugehörigen Websites** nicht ändern. Die Liste der zugehörigen Websites wird als Referenz bereitgestellt, damit Sie wissen, welche Websites beeinträchtigt werden, wenn Sie die Regionseinstellungen ändern.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen vorhandener netzwerkregionen in lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Konfigurieren von netzwerkregionen für CAC in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

