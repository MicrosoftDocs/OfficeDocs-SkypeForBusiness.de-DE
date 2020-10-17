---
title: 'Lync Server 2013: Löschen vorhandener netzwerkregionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3a1c1e697e681eec4886dca9e942d9bc133b0f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525402"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Löschen vorhandener netzwerkregionen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können lync Server-Systemsteuerung zum Konfigurieren von netzwerkregionen verwenden. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. Im lync Server-Systemsteuerung können Sie eine netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um vorhandene netzwerkregionen zu löschen. Ausführliche Informationen zum Erstellen oder Ändern vorhandener netzwerkregionen finden Sie unter [erstellen oder Ändern von netzwerkregionen in lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>So löschen Sie eine netzwerkregion

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehr als eine Region gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie bei gedrückter STRG-Taste mehrere Regionen aus. Wenn Sie alle Regionen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Eine netzwerkregion kann nicht entfernt werden, wenn Sie einem Netzwerkstandort zugeordnet ist. Wenn Sie versuchen, eine Region zu entfernen, die einer Website zugeordnet ist, wird eine Fehlermeldung angezeigt. Wenn Sie sehen möchten, ob eine Region einem Standort zugeordnet ist, wählen Sie die Region aus, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von netzwerkregionen in lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

