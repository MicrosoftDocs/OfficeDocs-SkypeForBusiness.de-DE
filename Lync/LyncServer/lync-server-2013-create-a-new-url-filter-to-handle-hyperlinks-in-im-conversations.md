---
title: Erstellen eines neuen URL-Filters zur Behandlung von Hyperlinks in Chat Unterhaltungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b129f2f9f1aa4b9a2a07a63d0432957f2b79941
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501912"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Zusätzlich zum Ändern des globalen URL-Filters können Sie benutzerdefinierte URL-Filter für einzelne Websites in ihrer lync Server 2013-Bereitstellung konfigurieren. Ausführliche Informationen zur URL-Filterung finden Sie unter [Configuring File Transfer and URL Filtering for Instant Messaging (Sofortnachrichten) in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>So erstellen Sie einen neuen URL-Filter

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** und dann auf **URL-Filter**.

4.  Klicken Sie auf der Seite **URL-Filter** auf **Neu**.

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, für den Sie den URL-Filter erstellen möchten, und klicken Sie anschließend auf **OK**.

6.  Aktivieren Sie im Dialogfeld **Neuer URL-Filter** das Kontrollkästchen **URL-Filter aktivieren**, um die URL-Filterung für den Standort zu aktivieren.

7.  Wenn Sie alle aktiven URLs blockieren möchten, die eine Datei mit einer der unter **Dateityperweiterungen, die blockiert werden sollen** aufgeführten Erweiterungen enthalten, aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **URLs mit Dateierweiterung blockieren**.

8.  Klicken Sie im Dropdown-Listenfeld **Linkpräfix** auf die gewünschte Option zur Verarbeitung von URLs in Sofortnachrichtenunterhaltungen.
    
    Über die Option **Nachricht zulassen** wird dem Benutzer beim Senden eines zulässigen Links eine Warnmeldung angezeigt.

9.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Ändern des standardmäßigen URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

