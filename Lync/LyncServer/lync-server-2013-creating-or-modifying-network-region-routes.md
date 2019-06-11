---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerkbereichs Routen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f31daafe6cafbf74f9f12812f8259c24cfa7349
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Erstellen oder Ändern von Netzwerkbereichs Routen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-08_

Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird. Sie können die lync Server-Systemsteuerung verwenden, um Netzwerkbereichs Routen zu konfigurieren. In der lync Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um eine Netzwerk Regions Route zu erstellen oder zu ändern. Details zum Löschen vorhandener Netzwerkbereichs Routen finden Sie unter [Löschen vorhandener Netzwerkbereichs Routen in lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>So erstellen Sie eine Netzwerk Regions Route

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Route**.

4.  Klicken Sie auf der Seite **Region Route** auf **neu**.

5.  Geben **** Sie in das Feld Name einen Wert in das Feld **Name** ein.
    
    <div>
    

    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Microsoft lync Server 2013-Bereitstellung eindeutig sein.

    
    </div>

6.  Wählen Sie in der Dropdownliste **netzwerkregion \#1** einen der beiden Regionen aus, die mit dieser Route verbunden werden sollen.

7.  Wählen Sie in der Dropdownliste **netzwerkregion \#2** den anderen Bereich für diese Route aus. Diese Region muss sich von der für netzwerkregion \#1 ausgewählten Region unterscheiden.

8.  Verwenden Sie das Listenfeld **Netzwerk Gebiets Links** , um der Route Bereichs Links hinzuzufügen. Klicken Sie auf die Schaltfläche **Hinzufügen** , um die Seite **Regions Link** anzuzeigen. Klicken Sie auf einen Regions Link, der zu dieser Route hinzugefügt werden soll, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Klicken Sie weiter auf die Schaltfläche <STRONG>Hinzufügen</STRONG> , um weitere Links hinzuzufügen, oder wählen Sie einen Link aus, und klicken Sie auf <STRONG>Entfernen</STRONG> , um einen Link zu entfernen.

    
    </div>

9.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>So ändern Sie eine Route des Netzwerkbereichs

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Route**.

4.  Klicken Sie auf der Seite **Region Route** auf die Route, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  In der **Route "Region bearbeiten**" können Sie die Regionen ändern, die mit dieser Route verbunden sind, und die der Route zugeordneten Regions Verknüpfungen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen vorhandener Netzwerkbereichs Routen in lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

