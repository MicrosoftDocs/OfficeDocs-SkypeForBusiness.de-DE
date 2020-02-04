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
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Löschen vorhandener netzwerkregionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg. Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird. Sie können die lync Server-Systemsteuerung verwenden, um netzwerkregionen zu konfigurieren. Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der lync Server-Systemsteuerung können Sie einen Netzwerkbereich erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um vorhandene netzwerkregionen zu löschen. Details zum Erstellen oder Ändern vorhandener netzwerkregionen finden Sie unter [erstellen oder Ändern von netzwerkregionen in lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>So löschen Sie einen Netzwerkbereich

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf den Bereich, den Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehr als einen Bereich gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Bereiche aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Bereiche auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Eine netzwerkregion kann nicht entfernt werden, wenn Sie einer Netzwerk Website zugeordnet ist. Wenn Sie versuchen, einen Bereich zu entfernen, der einer Website zugeordnet ist, wird eine Fehlermeldung angezeigt. Wenn Sie feststellen möchten, ob ein Bereich Websites zugeordnet ist, wählen Sie den Bereich aus, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .

    
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

