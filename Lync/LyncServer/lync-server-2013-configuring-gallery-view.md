---
title: 'Lync Server 2013: Konfigurieren der Katalogansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fd9823ca211242e0fd317e8a62ea118ed91a82f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517462"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a>Konfigurieren der Katalogansicht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

In lync Server 2013 konfigurieren Sie Videokonferenzen für die Galerieansicht in der konferenzrichtlinie. Die Galerieansicht ist standardmäßig aktiviert. Wenn Sie nicht möchten, dass die Galerieansicht verwendet wird, oder wenn diese Ansicht nur von bestimmten Benutzern verwendet werden soll, müssen Sie diese Funktion in der Konferenzrichtlinie deaktivieren.

Wenn das Video eines Konferenzteilnehmers nicht verfügbar ist, kann die Benutzeroberfläche der Galerieansicht verbessert werden, wenn Sie hochauflösende Fotos bereitstellen, ein neues Feature in lync Server 2013. Hochauflösende Fotos bieten eine Alternative zu den kleineren, begrenzten Auflösungen von Kontaktfotos, die in Active Directory-Domänendienste gespeichert sind. Hochauflösende Fotos werden im Exchange 2013 Postfach eines Benutzers gespeichert und erfordern daher die Integration von lync Server 2013 mit Exchange 2013. Ausführliche Informationen finden Sie im NextHop-Blog Artikel "integrieren von Exchange 2013 und lync Server 2013" unter [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) .

<div>


> [!NOTE]  
> Der Inhalt jedes Blogs und die dazugehörige URL kann ohne vorherige Ankündigung geändert werden.



</div>

Sie können die Parameter der Katalogansicht mithilfe lync Server 2013 Systemsteuerung oder mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsConferencingPolicy**

  - **Gruppe-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Konfigurieren der Galerieansicht mit den folgenden Konferenzrichtlinieneinstellungen:

  - **AllowMultiview**     Dieser Parameter steuert, ob ein Benutzer die Videokonferenzen für die Galerieansicht organisieren darf. Die Festlegung des Parameters gilt für geplante Besprechungen ebenso wie für Ad-hoc-Besprechungen, die vom Benutzer erstellt werden.
    
    Beispiele:
    
      - Dieser Parameter ist für Benutzer a, der in einem lync Server 2013 Pool verwaltet wird, auf true festgelegt. Von Benutzer A organisierte Besprechungen ermöglichen Benutzern das Hinzufügen und empfangen mehrerer Videostreams.
    
      - Dieser Parameter wird für Benutzer B auf "false" festgelegt, der in einem lync Server 2013 Pool verwaltet wird. Von Benutzer B organisierte Besprechungen weisen einen einzelnen Videostream auf, der der von lync Server 2010 bereitgestellten Videokonferenz ähnelt.
    
    Dieser Parameter legt fest, welche Benutzer Besprechungen mit mehreren Videostreams organisieren können. Teilnehmer von Besprechungen, bei denen mehrere Videostreams zulässig sind, können diese empfangen, wenn sie dazu berechtigt sind (siehe Beschreibung für den EnableMultiviewJoin-Parameter). Andernfalls ist dies nicht möglich.

  - **EnableMultiviewJoin**     Mit diesem Parameter wird gesteuert, ob ein Teilnehmer an einer Besprechung in Besprechungen, die ihn zulassen, das Videoerlebnis "Gallery View" erhält. Der Parameter wirkt sich auf alle Besprechungen aus, an denen ein Benutzer teilnimmt.
    
    Beispiele:
    
      - Dieser Parameter ist für Benutzer c auf true festgelegt. Benutzer c kann mehrere Videostreams empfangen, wenn er an einer Besprechung teilnimmt, die von Benutzer a organisiert oder gestartet wird. Benutzer c erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bei der Teilnahme an einer von Benutzer B organisierten oder gestarteten Besprechung bereitgestellt wurde.
    
      - Dieser Parameter wird für Benutzer d auf "false" festgelegt. Benutzer d erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bei der Teilnahme an einer von Benutzer a oder Benutzer B organisierten Besprechung bereitgestellt wird.

Das folgende Verfahren ist ein Beispiel für die Verwendung von lync Server-Verwaltungsshell zum Aktivieren von Videokonferenzen in der Galerieansicht.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>So bearbeiten Sie die Konferenzrichtlinie für Videokonferenzen in der Galerieansicht

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet über die Befehlszeile aus, um die Konferenzrichtlinie zu bearbeiten:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

