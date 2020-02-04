---
title: 'Lync Server 2013: Löschen einer vorhandenen Netzwerk Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c8e3828bccb84fcddb4404dd7228173c63ab8a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Löschen einer vorhandenen Netzwerk Website in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind. Sie können die lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen. Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein. Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist. In der lync Server-Systemsteuerung können Sie Netzwerk Websites erstellen, ändern und löschen. Gehen Sie wie folgt vor, um eine vorhandene Netzwerk Website zu löschen. Details zum Erstellen oder Ändern von Netzwerk Websites finden Sie unter [erstellen oder Ändern von Netzwerk Websites in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>So löschen Sie eine Netzwerk Website

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehr als eine Website gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Websites aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Websites auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Sie können eine Netzwerk Website nicht entfernen, wenn Sie einem Netzwerk-Subnetz zugeordnet ist. Wenn Sie versuchen, eine Website zu entfernen, die einem Subnetz zugeordnet ist, wird eine Fehlermeldung angezeigt. Wenn Sie feststellen möchten, ob eine Website mit Subnetzen verknüpft ist, klicken Sie auf die Website, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

