---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerk Regions Routen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cdc05978b6fb8d81c81995d7b089d14ed4bec3b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516742"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Erstellen oder Ändern von Netzwerk Regions Routen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-08_

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Sie können lync Server-Systemsteuerung verwenden, um Netzwerk Regions Routen zu konfigurieren. In lync Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um eine Netzwerk Regions Route zu erstellen oder zu ändern. Ausführliche Informationen zum Löschen einer vorhandenen Netzwerk Regions Routen finden Sie unter [Löschen vorhandener Netzwerk Regions Routen in lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>So erstellen Sie eine Netzwerkregionenroute

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf **Neu**.

5.  Geben Sie im Abschnitt **Neue Regionenroute** im Feld **Name** einen Wert ein.
    
    <div>
    

    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Microsoft lync Server 2013-Bereitstellung eindeutig sein.

    
    </div>

6.  Wählen Sie in der Dropdownliste **netzwerkregion \# 1** eine der zwei Regionen aus, die über diese Route verbunden werden sollen.

7.  Wählen Sie in der Dropdownliste **netzwerkregion \# 2** den anderen Bereich für diese Route aus. Diese Region muss sich von der für die netzwerkregion 1 ausgewählten Region unterscheiden \# .

8.  Fügen Sie der Route über das Listenfeld **Netzwerkregionenverbindungen** Regionenverbindungen hinzu. Klicken Sie auf die Schaltfläche **Hinzufügen**, um die Seite **Regionenverbindung** anzuzeigen. Klicken Sie auf eine Regionenverbindung, die Sie dieser Route hinzufügen möchten, und klicken Sie anschließend auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Klicken Sie erneut auf die Schaltfläche <STRONG>Hinzufügen</STRONG>, um weitere Verbindungen hinzuzufügen, oder wählen Sie eine Verbindung aus, und klicken Sie auf <STRONG>Entfernen</STRONG>, um eine Verbindung zu entfernen.

    
    </div>

9.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>So ändern Sie eine Netzwerkregionenroute

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  In **Regionenroute bearbeiten** können Sie die über diese Route verbundenen Regionen und die der Route zugeordneten Regionenverbindungen ändern.

7.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen vorhandener Netzwerk Regions Routen in lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

