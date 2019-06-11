---
title: 'Lync Server 2013: Erstellen eines neuen dateiübertragungsfilters für eine bestimmte Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ddb23081acba6eb208607a0bacddb7b403468b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für eine bestimmte Website

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Zusätzlich zum Ändern des globalen dateiübertragungsfilters können Sie benutzerdefinierte Dateiübertragungsfilter für bestimmte Websites in ihrer lync Server 2013-Bereitstellung konfigurieren. Details zum Filtern von Dateiübertragungen finden Sie unter [Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>So erstellen Sie einen Dateiübertragungsfilter für eine bestimmte Website

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** , und klicken Sie dann auf **Datei Filter**.

4.  Klicken Sie auf der Seite **Datei Filter** auf **neu**.

5.  Klicken Sie im Dialogfeld **Website auswählen** auf die Website, für die Sie den Dateiübertragungsfilter erstellen möchten, und klicken Sie dann auf **OK**.

6.  Klicken Sie in **neuer Dateifilter**auf das Kontrollkästchen **Dateifilter aktivieren** .

7.  Klicken Sie im Dropdown-Listenfeld **Dateiübertragung** auf **Alle blockieren** oder **bestimmte Dateitypen blockieren**.

8.  Wenn Sie auf **Alle blockieren**geklickt haben, fahren Sie mit Schritt 10 fort.

9.  Wenn Sie auf **bestimmte Dateitypen blockieren**geklickt haben, gehen Sie folgendermaßen vor:
    
    1.  Klicken Sie auf **auswählen** , um die Standardliste der Dateitypen Erweiterungen zu ändern, die Sie blockieren möchten.
    
    2.  Wählen Sie im Dialogfeld **Dateityp** auswählen die Dateitypen aus, die Sie blockieren oder zulassen möchten, indem Sie deren Erweiterungen aus den Kategorien unter **Dateityperweiterungen**hinzufügen oder entfernen.
    
    3.  Wenn die Erweiterung für einen Dateityp, den Sie blockieren möchten, nicht angezeigt wird, geben Sie die Erweiterung in das Textfeld unter **Hinzufügen von Dateityperweiterungen zur Liste**ein, und klicken Sie dann auf **Hinzufügen**.
    
    4.  Klicken Sie auf **OK**.

10. Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Ändern des Standard-URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

