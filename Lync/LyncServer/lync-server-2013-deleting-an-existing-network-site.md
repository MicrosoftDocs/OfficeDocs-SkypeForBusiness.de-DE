---
title: 'Lync Server 2013: Löschen eines vorhandenen Netzwerkstandorts'
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
ms.openlocfilehash: 5b67dcb92fec16c31c2e2a6be780a29eb1eee295
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Löschen eines vorhandenen Netzwerkstandorts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind. Sie können die lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie Regionen zuzuordnen. Eine Netzwerkregion für Nordamerika ist beispielsweise Netzwerkstandorten wie Chicago, Redmond und Vancouver zugeordnet. Ein Anrufsteuerungsdienst-Netzwerkstandort muss für jeden Standort einer Organisation erstellt werden, selbst wenn der jeweilige Standort keine Bandbreiteneinschränkungen aufweist. In der lync Server-Systemsteuerung können Sie Netzwerkstandorte erstellen, ändern und löschen. Verwenden Sie das folgende Verfahren, um einen vorhandenen Netzwerkstandort zu löschen. Ausführliche Informationen zum Erstellen oder Ändern von Netzwerkstandorten finden Sie unter [erstellen oder Ändern von Netzwerkstandorten in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>So löschen Sie einen Netzwerkstandort

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehrere Standorte in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Standorte aus. Wenn Sie alle Standorte auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Ein Netzwerkstandort kann nicht gelöscht werden, wenn er einem Netzwerksubnetz zugeordnet ist. Wenn Sie versuchen, einen einem Subnetz zugeordneten Standort zu entfernen, wird eine Fehlermeldung ausgegeben. Um zu überprüfen, ob ein Standort einem Subnetz zugeordnet ist, klicken Sie auf den Standort und anschließend im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

