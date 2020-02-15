---
title: 'Lync Server 2013: Erstellen eines neuen dateiübertragungsfilters für einen bestimmten Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 911f01c4ce104c3cdd641a793065c14bed43abb4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Zusätzlich zum Ändern des globalen dateiübertragungsfilters können Sie benutzerdefinierte Dateiübertragungsfilter für bestimmte Websites in ihrer lync Server 2013-Bereitstellung konfigurieren. Ausführliche Informationen zur Dateiübertragungsfilterung finden Sie unter [Configuring File Transfer and URL Filtering for Instant Messaging (Sofortnachrichten) in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>So erstellen Sie einen Dateiübertragungsfilter für einen spezifischen Standort

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** und dann auf **Dateifilter**.

4.  Klicken Sie auf der Seite **Dateifilter** auf **Neu**.

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, für den Sie den Dateiübertragungsfilter erstellen möchten, und klicken Sie anschließend auf **OK**.

6.  Aktivieren Sie im Abschnitt **Neuer Dateifilter** das Kontrollkästchen **Dateifilter aktivieren**.

7.  Klicken Sie im Dropdown-Listenfeld **Dateiübertragung** auf **Alles blockieren** oder **Bestimmte Dateitypen blockieren**.

8.  Wenn Sie auf **Alles blockieren** geklickt haben, fahren Sie mit Schritt 10 fort.

9.  Führen Sie eine der folgenden Aktionen aus, wenn Sie auf die Option **Bestimmte Dateitypen blockieren** geklickt haben:
    
    1.  Klicken Sie auf **Auswählen**, um die standardmäßige Liste der Erweiterungen für Dateitypen zu ändern, die blockiert werden sollen.
    
    2.  Wählen Sie im Dialogfeld **Dateityp auswählen** die Dateitypen aus, die Sie blockieren oder zulassen möchten, indem Sie die zugehörigen Erweiterungen aus den Kategorien unter **Dateityperweiterungen** entfernen oder sie hinzufügen.
    
    3.  Wenn die Erweiterung des gewünschten Dateityps nicht aufgeführt wird, geben Sie die Erweiterung in das Textfeld unter **Dateityperweiterungen der Liste hinzufügen** ein, und klicken Sie anschließend auf **Hinzufügen**.
    
    4.  Klicken Sie auf **OK**.

10. Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Ändern des standardmäßigen URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

