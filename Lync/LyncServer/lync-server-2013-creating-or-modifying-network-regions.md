---
title: 'Lync Server 2013: Erstellen oder Ändern von netzwerkregionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52518c76efdb302661ed3f097cb382d399299798
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Erstellen oder Ändern von netzwerkregionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können lync Server-Systemsteuerung zum Konfigurieren von netzwerkregionen verwenden. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. Im lync Server-Systemsteuerung können Sie eine netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema zum Erstellen und Ändern von Netzwerkregionen. Ausführliche Informationen zum Löschen vorhandener netzwerkregionen finden Sie unter [Löschen vorhandener netzwerkregionen in lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>So erstellen Sie eine Netzwerkregion

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf **Neu**.

5.  Geben Sie auf der Seite **Neue Region** im Feld **Name** einen Wert ein. Dieser Wert muss innerhalb Ihrer Microsoft lync Server 2013-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Zentraler Standort** den zentralen Standort für diese Netzwerkregion aus.

7.  Das Kontrollkästchen **Alternativen Audiopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

8.  Das Kontrollkästchen **Alternativen Videopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

9.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu dieser Region ein, die nicht durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit ausführen**.

Die Tabelle **Zugeordnete Standorte** wird zum Erstellen einer Netzwerkregion nicht verwendet. Sie ordnen einer Region einen Standort zu, wenn Sie den Standort erstellen oder ändern. Ausführliche Informationen finden Sie unter [erstellen oder Ändern von Netzwerkstandorten in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>So ändern Sie eine Netzwerkregion

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.

6.  Auf der Seite **Region bearbeiten** können Sie die Einstellungen zum Aktivieren und Deaktivieren von alternativen Pfaden für Audio und Video ändern, und Sie können die Beschreibung bearbeiten (ausführliche Informationen finden Sie unter "So erstellen Sie eine Netzwerkregion" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

Sie können die Option **Zugeordnete Standorte** auf dieser Seite nicht ändern. Die Liste der zugeordneten Standorte wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Standorte sich die Änderung der Regioneneinstellungen auswirkt.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen vorhandener netzwerkregionen in lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Konfigurieren von netzwerkregionen für die Anrufsteuerung in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Gruppe-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

