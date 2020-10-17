---
title: 'Lync Server 2013: Übersicht über die gruppenanrufannahme'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c618664cb696a149cb56252cac2fba31548808ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521022"
---
# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Übersicht über die gruppenanrufannahme in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-12_

Group Call Pickup, ein neues Feature in kumulierten Updates für lync Server 2013: Februar 2013, ermöglicht Benutzern, eingehende Anrufe an Ihre Kollegen von ihren eigenen Telefonen aus zu beantworten. Dieses neue Feature erhöht die Verfügbarkeit einer Benutzer Leitung, indem andere Benutzer einen eingehenden Anruf annehmen können, indem Sie die Nummer einer Anrufannahme Gruppe wählen. Wenn die gruppenanrufannahme bereitgestellt wird, kann die Anzahl der eingehenden Anrufe, die an Voicemail weitergeleitet werden, erheblich reduziert werden, was besonders nützlich für Anrufe von Kunden ist, die sich außerhalb Ihrer Organisation befinden.

Das Feature für die gruppenanrufannahme wurde speziell für Geschäftseinheiten in offenen Office-Umgebungen entwickelt. Eingehende Anrufe sind nicht störend, da Sie nur am vorgesehenen Bestimmungsort Klingeln. Andere Benutzer, die den Ring hören, können den Anruf jedoch auch einfach durch Wählen der Gruppennummer abholen.

In Umgebungen, in denen sich Benutzer nicht in einem offenen Office-Layout befinden oder wenn Benutzer, die eine gemeinsame Verantwortung teilen, geografisch verteilt sind, stellt die Team Anruf Lösung die am besten geeignete Lösung dar. Der Hauptunterschied zwischen der gruppenanrufannahme und dem Teamanruf besteht darin, dass bei der gruppenanrufannahme ein eingehender Anruf nur am vorgesehenen Ziel klingelt, aber jeder kann trotzdem entscheiden, ob er eine Antwort erhalten möchte, indem er eine Gruppennummer wählt. Bei einem Teamanruf klingelt der Anruf an allen Telefonen der Teammitglieder, und jeder Benutzer im Team kann das Telefon abholen, um den Anruf entgegenzunehmen. Ein weiterer Unterschied zwischen der gruppenanrufannahme und dem Team Anruf besteht darin, dass die gruppenanrufannahme über lync Server von einem Administrator verwaltet wird. Mit dem Team Anruf verwalten Endbenutzer das Feature mithilfe des lync-Clients. Bei der gruppenanrufannahme kann daher dieser Aspekt der Anrufverwaltung zentralisiert werden.

Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen. Wenn Sie die gruppenanrufannahme bereitstellen, konfigurieren Sie die Orbit-Tabelle für das Parken von Anrufen mit getrennten Bereichen von Durchwahlnummern, die als Nummern für die Anrufannahme Gruppe festgelegt sind. Wie die Umlaufbahn Nummern für die Anrufannahme müssen Gruppennummern für die Anrufannahme virtuelle Erweiterungen sein, denen kein Benutzer oder Telefon zugewiesen ist. Jede Front-End-Pool, in der Sie die gruppenanrufannahme bereitstellen, kann über einen oder mehrere Bereiche der Anrufannahme Gruppennummern verfügen. Die Gruppennummern Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.

<div>


> [!NOTE]  
> Nummernbereiche, die als Gruppenanruf-Abhol Nummern in der Orbit-Tabelle für das Parken von Anrufen festgelegt sind, können nicht mithilfe der lync Server-Systemsteuerung verwaltet oder angezeigt werden. Die einzige Möglichkeit zum Anzeigen aller Nummernbereiche in der Orbit-Tabelle für das Parken von anrufen ist die Verwendung lync Server-Verwaltungsshell. Auf ähnliche Weise ist die einzige Möglichkeit zum Hinzufügen, ändern oder Entfernen von Gruppenanruf-Pickup-Nummern die Verwendung lync Server-Verwaltungsshell.



</div>

Nachdem Sie die Nummern für die Anrufannahme Gruppe konfiguriert haben, weisen Sie Benutzer einer Anrufannahme Gruppe zu. Jeder Benutzer, der einer Anrufannahme Gruppe zugewiesen ist, kann seine Anrufe von anderen Benutzern beantworten lassen. Wenn ein Anruf an einen Benutzer übertragen wird, der einer Anrufannahme Gruppe zugewiesen ist, kann jeder andere Benutzer, der den Anruf bemerkt, ihn beantworten, indem er die Nummer der Anrufannahme Gruppe manuell anwählt. Der Benutzer, der den Anruf annimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer abgeholt wird, wird eine Benachrichtigung an die ursprünglich angerufene Nummer gesendet.

<div>


> [!NOTE]  
> Ein Benutzer kann nur Mitglied einer Anrufannahme Gruppe sein.



</div>

<div>


> [!NOTE]  
> Jeder Benutzer in der lync Server-Bereitstellung kann zwar einen Anruf an ein Mitglied der Anrufannahme Gruppe annehmen, aber die Person, die den Anruf annimmt, muss die richtige Nummer für die Anrufannahme Gruppe kennen, um zu wählen.



</div>

Wenn ein Benutzer eine Anrufannahme-Gruppennummer zum Annehmen eines Anrufs wählt, wenn mehrere Telefone in der Gruppe Klingeln, antwortet der Benutzer mit dem Anruf, der am längsten klingelt.

Die Einstellungen für das gleichzeitige Klingeln sind für Benutzer mit gruppenanrufannahme funktionsfähig. Das bedeutet, dass ein Anruf, der an einen Benutzer mit gruppenanrufannahme erfolgt, für alle konfigurierten Ziele klingelt und ein anderer Benutzer den Anruf annehmen kann. Die Ausnahme zu dieser Regel besteht darin, dass der Benutzer das gleichzeitige Klingeln so konfiguriert, dass alle Teammitglieder aufgerufen werden.

Die gruppenanrufannahme kann nicht zur Beantwortung der folgenden Anruftypen verwendet werden:

  - Anrufe an eine privatleitungen

  - Anrufe von einem Kontakt, dem die Datenschutz Beziehung "Freunde und Familie" zugewiesen wurde
    
    <div>
    

    > [!TIP]  
    > Ein Benutzer, der Mitglied einer Anrufannahme Gruppe ist, kann verhindern, dass bestimmte Anrufe über die gruppenanrufannahme abgerufen werden, indem der Kontakt als persönlicher Kontakt im lync-Client gekennzeichnet wird. Wenn Sie einen Kontakt als persönlichen Kontakt markieren möchten, legen Sie die Datenschutz Beziehung für den Kontakt auf "Freunde und Familie" fest. Alle eingehenden Anrufe von Kontakten mit der Datenschutz Beziehung, die auf Freunde und Familie festgelegt sind, können nicht mithilfe der gruppenanrufannahme abgerufen werden.

    
    </div>

  - Video Teil von Audio/Video-anrufen
    
    <div>
    

    > [!NOTE]  
    > Wenn ein Benutzer auf einen Audio/Video-Anruf antwortet, erhält der Benutzer nur die Audiodaten. Entweder der Anrufer oder die Person, die den Anruf annimmt, kann den Anruf eskalieren, um Video hinzuzufügen.

    
    </div>

  - Gleichzeitiges Klingeln von anrufen, die an Team Anruf Mitglieder weitergeleitet werden

  - An eine Stellvertretung weitergeleitete Anrufe

  - An eine Reaktionsgruppe weitergeleitete Anrufe

Die folgenden Benutzertypen können nicht an der gruppenanrufannahme teilnehmen. Das heißt, Sie sollten nicht in eine gruppenanrufannahme Gruppe aufgenommen werden, und Sie können keine Anrufe für Benutzer abholen, für die die gruppenanrufannahme aktiviert ist.

  - Benutzer, die Online in einer hybridbereitstellung verwaltet werden

  - Benutzer, die nicht in einem lync Server 2013 Pool mit kumulierten Updates für lync Server 2013 verwaltet werden: 2013. Februar in einer lokalen Bereitstellung

Wenn niemand einen Anruf an ein Mitglied einer Anrufannahme Gruppe beantwortet, wird der Anruf wie in den Clienteinstellungen angegeben weitergeleitet. Das heißt, der Anruf geht an Voicemail oder wird an ein anderes Ziel weitergeleitet, wie in den Clienteinstellungen angegeben.

</div>

<span> </span>

</div>

</div>

</div>

