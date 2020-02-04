---
title: 'Lync Server 2013: Ändern des standardmäßigen dateiübertragungsfilters'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a0d9ade3fd750f5dc89526969bad7e39ad0f35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Lync Server 2013 bietet einen globalen Dateiübertragungsfilter, der bestimmte Dateitypen während der folgenden dateibezogenen Aktivitäten innerhalb ihrer lync Server 2013-Bereitstellung blockiert:

  - Dateiübertragungsanforderungen während Chat Unterhaltungen (Sofortnachrichten)

  - Hochladen und Herunterladen von Dateien beim Verwenden des Handzettel Features im Office Live Meeting 2007-Client

  - Multimedia-Wiedergabe während Konferenzen

Je nach den Dateitypen, die Sie blockieren oder zulassen möchten, können Sie den globalen Filter mithilfe der lync Server-Systemsteuerung ändern. Details zum Filtern von Dateiübertragungen finden Sie unter [Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>So ändern Sie den standardmäßigen Dateiübertragungsfilter

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** , und klicken Sie dann auf **Datei Filter**.

4.  Doppelklicken Sie auf der Seite **Dateifilter** auf den **globalen** Filter.

5.  Aktivieren Sie unter **Dateifilter bearbeiten**das Kontrollkästchen **Dateifilter aktivieren** .

6.  Klicken Sie im Dropdown-Listenfeld **Dateiübertragung** auf **Alle blockieren** oder **bestimmte Dateitypen blockieren**.

7.  Wenn Sie auf **Alle blockieren**geklickt haben, fahren Sie mit Schritt 9 fort.

8.  Wenn Sie auf **bestimmte Dateitypen blockieren**geklickt haben, gehen Sie folgendermaßen vor:
    
    1.  Klicken Sie auf **auswählen** , um die Standardliste der Dateitypen Erweiterungen zu ändern, die Sie blockieren möchten.
    
    2.  Wählen Sie unter **Dateityp**auswählen die Dateitypen aus, die Sie blockieren oder zulassen möchten, indem Sie deren Erweiterungen aus den Kategorien unter **Dateityperweiterungen**hinzufügen oder entfernen.
    
    3.  Wenn die Erweiterung für einen Dateityp, den Sie blockieren möchten, nicht angezeigt wird, geben Sie die Erweiterung in das Textfeld unter **Hinzufügen von Dateityperweiterungen zur Liste**ein, und klicken Sie dann auf **Hinzufügen**.
    
    4.  Klicken Sie auf **OK**.

9.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für eine bestimmte Website](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Ändern des Standard-URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

