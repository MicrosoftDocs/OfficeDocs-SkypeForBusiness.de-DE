---
title: 'Lync Server 2013: Löschen von Netzwerk Regions Links'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19835235921c10c0b3fe2be7d9c269a36dff7b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a>Löschen von Netzwerk Regions Links in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren. Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden. Sie können die lync Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen zu löschen. Ausführliche Informationen zum Erstellen oder Ändern der Netzwerk Regions Verknüpfung finden Sie unter [Configuring Network Region Links in lync Server 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>So löschen Sie eine Netzwerkregionenverbindung

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehrere Regionenverbindungen in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Netzwerkregionen aus. Wenn Sie alle Netzwerkregionen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.

    
    </div>

5.  Wählen Sie im Menü **Bearbeiten** die Option **Löschen** aus.

6.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Netzwerk Regions Links in lync Server 2013](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

