---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen Richtlinienregel für Clientversionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Erstellen oder Ändern einer neuen Richtlinienregel für Clientversionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-21_

Client Versionsrichtlinien Regeln definieren die Aktionen, die ausgeführt werden sollen, wenn Benutzer versuchen, sich mit bestimmten Clients und Clientversionen anzumelden. Sie können in der lync Server 2013-Systemsteuerung einzelne Regeln für eine clientversionsrichtlinie erstellen oder ändern.

<div>


> [!IMPORTANT]  
> Regeln werden in der Reihenfolge der Rangfolge aufgelistet. Wenn Sie beispielsweise über eine Regel verfügen, mit der Clients, auf denen Version 1,5 ausgeführt wird, eine Verbindung herstellen können, gefolgt von einer Regel, die Clients mit einer älteren Version als 2,0 blockiert, hat die erste Regel Vorrang, und Clients, auf denen Version 1,5 ausgeführt wird, können eine Verbindung herstellen.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>So erstellen oder ändern Sie clientversionsrichtlinien Regeln mit der lync Server-Systemsteuerung

1.  [Erstellen oder Ändern einer neuen clientversionsrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) mit der lync Server-Systemsteuerung.

2.  Führen Sie auf der Seite **Client-Versionsrichtlinie bearbeiten** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **neu** , um eine neue clientversionsregel zu erstellen.
    
      - Klicken Sie in der Liste auf einen der definierten Clienttypen, und klicken Sie dann auf **Details anzeigen**.
    
    <div>
    

    > [!NOTE]  
    > Sie können Platzhalter zum Angeben des Clienttyps verwenden.

    
    </div>

3.  Wählen Sie im **Benutzer-Agent**einen Clienttyp aus.

4.  Führen Sie unter **Versionsnummer**die folgenden Aktionen aus:
    
      - Geben Sie in der **Hauptversion**die Nummer ein, die der Hauptversion des Clients entspricht.
    
      - Geben Sie in der **Nebenversion**die Zahl ein, die der Nebenversion des Clients entspricht.
    
      - Geben Sie in **Build**die Zahl ein, die der Haupt-und Nebenversion des Clients entspricht.
    
      - Geben Sie in **Update**die Nummer ein, die der aktualisierten Version des Clients entspricht.
    
    <div>
    

    > [!NOTE]  
    > Sie können Platzhalter verwenden, um die Versionsnummer des Clients anzugeben.

    
    </div>

5.  Wenn Sie den übereinstimmenden Vorgang für die Client Version angeben möchten, die Sie in den vorherigen Schritten angegeben haben, klicken Sie im **Vergleichsvorgang**auf eine der folgenden Optionen:
    
      - **Identisch mit**
    
      - **Ist nicht**
    
      - **Neuer als**
    
      - **Neuer als oder identisch mit**
    
      - **Älter als**
    
      - **Älter als oder identisch mit**

6.  Wenn Sie die Aktion angeben möchten, die ausgeführt werden soll, wenn die Kriterien in den vorherigen Schritten erfüllt sind, klicken Sie in **Aktion**auf eine der folgenden Optionen:
    
      - Klicken Sie auf **zulassen**, damit sich der Client anmelden kann.
    
      - Wenn Sie zulassen möchten, dass der Client sich beim Windows Server Update-Dienst oder Microsoft Update anmeldet und Updates erhält, klicken Sie auf **zulassen und aktualisieren**. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, wenn sich die Benutzer das nächste Mal bei lync 2013 anmelden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.

        
        </div>
    
      - Klicken Sie auf **Allow with URL**, damit der Client sich anmelden und eine Meldung darüber anzeigen kann, wo eine andere Client Version heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.
    
      - Klicken Sie auf **blockieren**, um zu verhindern, dass der Client sich anmeldet.
    
      - Klicken Sie auf **blockieren und aktualisieren**, um zu verhindern, dass der Client sich anmeldet und dem Client das Empfangen von Updates vom Windows Server Update-Dienst oder Microsoft Update ermöglicht. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.
    
      - Wenn Sie verhindern möchten, dass der Client sich anmeldet und eine Meldung darüber anzeigt, wo eine andere Client Version heruntergeladen werden soll, klicken Sie auf **mit URL blockieren**. Sie geben die URL später in diesem Verfahren an.

7.  Optional Wenn Sie im vorherigen Schritt auf **Allow with URL** oder **Block with URL** geklickt haben, geben Sie die Client Download-URL ein, die in die Nachricht in **URL**aufgenommen werden soll.

8.  Klicken Sie auf **OK**und dann auf **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

