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
ms.openlocfilehash: 3799b40cda71b446387b708dcdb85d69c1795de6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515192"
---
# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Lync Server 2013 stellt einen globalen Dateiübertragungsfilter bereit, der bestimmte Dateitypen während der folgenden dateibezogenen Aktivitäten in ihrer lync Server 2013-Bereitstellung blockiert:

  - Dateiübertragungsanforderungen während Sofortnachrichtenunterhaltungen

  - Dateiuploads und -downloads bei Verwendung der Ausdruckfunktion im Office Live Meeting 2007-Client

  - Multimediawiedergabe während Konferenzen

Abhängig von den Dateitypen, die Sie blockieren oder zulassen möchten, können Sie lync Server-Systemsteuerung verwenden, um den globalen Filter zu ändern. Ausführliche Informationen zur Dateiübertragungsfilterung finden Sie unter [Configuring File Transfer and URL Filtering for Instant Messaging (Sofortnachrichten) in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>So ändern Sie den standardmäßigen Dateiübertragungsfilter

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Instant Messaging und Anwesenheit** und dann auf **Dateifilter**.

4.  Doppelklicken Sie auf der Seite **Dateifilter** auf den Filter **Global**.

5.  Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Dateifilter aktivieren**.

6.  Klicken Sie im Dropdown-Listenfeld **Dateiübertragung** auf **Alle blockieren** oder **Bestimmte Dateitypen blockieren**.

7.  Wenn Sie die Option **Alle blockieren** aktiviert haben, fahren Sie mit Schritt 9 fort.

8.  Führen Sie eine der folgenden Aktionen aus, wenn Sie auf die Option **Bestimmte Dateitypen blockieren** geklickt haben:
    
    1.  Klicken Sie auf **Auswählen**, um die standardmäßige Liste der Erweiterungen für Dateitypen zu ändern, die blockiert werden sollen.
    
    2.  Wählen Sie im Dialogfeld **Dateityp auswählen** die Dateitypen aus, die Sie blockieren oder zulassen möchten, indem Sie die zugehörigen Erweiterungen aus den Kategorien unter **Dateityperweiterungen** entfernen oder sie hinzufügen.
    
    3.  Wenn die Erweiterung des gewünschten Dateityps nicht aufgeführt wird, geben Sie die Erweiterung in das Textfeld unter **Neue Dateityperweiterungen zur Liste hinzufügen** ein, und klicken Sie anschließend auf **Hinzufügen**.
    
    4.  Klicken Sie auf **OK**.

9.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Ändern des standardmäßigen URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

