---
title: 'Lync Server 2013: Konfigurieren der Katalogansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7333c1928bd92dbe6145f238d828e81bbeb3d868
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Konfigurieren der Katalogansicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In lync Server 2013 konfigurieren Sie Videokonferenzen in der Katalogansicht in Konferenzrichtlinien. Die Katalogansicht ist standardmäßig aktiviert. Wenn Sie die Katalogansicht nicht zulassen oder nur für einige Benutzer zulassen möchten, müssen Sie das Feature in Konferenzrichtlinien deaktivieren.

Wenn das Video eines Konferenzteilnehmers nicht zur Verfügung steht, kann die Benutzeroberfläche für die Galerieansicht verbessert werden, wenn Sie Fotos mit hoher Auflösung, ein neues Feature in lync Server 2013, bereitstellen. Fotos mit hoher Auflösung bieten eine Alternative zu den kleineren, in den Active Directory-Domänendiensten gespeicherten Kontaktfotos mit begrenzter Auflösung. Fotos mit hoher Auflösung werden im Exchange 2013-Postfach eines Benutzers gespeichert, und daher müssen Sie lync Server 2013 in Exchange 2013 integrieren. Ausführliche Informationen finden Sie im NextHop-Blog Artikel "Integration von Exchange 2013 und lync Server 2013" unter [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).

<div>


> [!NOTE]  
> Die Inhalte der Blogs und die zugehörige URL können ohne vorherige Ankündigung geändert werden.



</div>

Sie können die Parameter für die Katalogansicht mithilfe der lync Server 2013-Systemsteuerung oder mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Konfigurieren Sie die Katalogansicht mit den folgenden konferenzrichtlinieneinstellungen:

  - **AllowMultiview**   dieser Parameter steuert, ob ein Benutzer die Möglichkeit hat, Videokonferenzen in der Katalogansicht zu organisieren. Dieser Parameter gilt für geplante und Ad-hoc-Besprechungen, die vom Benutzer erstellt wurden.
    
    Beispiele
    
      - Dieser Parameter ist für Benutzer A auf true festgelegt, der in einem lync Server 2013-Pool verwaltet wird. Besprechungen, die von einem Benutzer organisiert werden, ermöglichen es Benutzern, mehreren Videostreams beizutreten und zu empfangen.
    
      - Dieser Parameter wird für Benutzer B auf "false" festgelegt, der sich in einem lync Server 2013-Pool befindet. Besprechungen, die von Benutzer B organisiert werden, sind mit einem einzelnen Videostream vergleichbar mit der Videokonferenz, die von lync Server 2010 bereitgestellt wird.
    
    Dieser Parameter bestimmt, wer Besprechungen organisieren kann, die mehrere Videostreams zulassen. Teilnehmern an Besprechungen, die mehrere Videostreams zulassen, ist es möglich, auf der Grundlage ihrer individuellen Berechtigungen mehrere Videostreams zu empfangen (siehe Beschreibung des EnableMultiviewJoin-Parameters).

  - **EnableMultiviewJoin**   dieser Parameter steuert, ob ein Teilnehmer an einer Besprechung in Besprechungen, die ihn zulassen, die videoerfahrung in der Galerieansicht erhält. Dieser Parameter steuert die Benutzererfahrung in jeder Besprechung, an der Sie teilnehmen.
    
    Beispiele
    
      - Dieser Parameter wird für Benutzer c auf "true" festgelegt, um mehrere Videostreams empfangen zu können, wenn Sie an einer Besprechung teilnehmen, die von Benutzer a organisiert oder gestartet wurde. Benutzer c erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bereitgestellt wird, wenn teilnehmen an einer Besprechung, die von Benutzer B organisiert oder gestartet wurde.
    
      - Dieser Parameter wird für Benutzer d auf "false" festgelegt und erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bei der Teilnahme an einer Besprechung, die von Benutzer a oder Benutzer B organisiert wurde, bereitgestellt wird.

Das folgende Verfahren ist ein Beispiel für die Verwendung der lync Server-Verwaltungsshell zum Aktivieren von Videokonferenzen in der Katalogansicht.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>So ändern Sie die konferenzrichtlinie für Videokonferenzen in der Katalogansicht

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie in der Befehlszeile das folgende Cmdlet aus, um die konferenzrichtlinie zu bearbeiten:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

