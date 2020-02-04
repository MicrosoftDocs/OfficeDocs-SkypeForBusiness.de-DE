---
title: 'Lync Server 2013: Übersicht über die Abholung von Gruppen anrufen'
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
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Übersicht über die Gruppenanruf Abholung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-12_

Der Gruppenanruf Pickup, ein neues Feature in kumulativen Updates für lync Server 2013: Februar 2013, ermöglicht Benutzern, eingehende Anrufe von ihren eigenen Telefonen an Ihre Kollegen zu beantworten. Dieses neue Feature erhöht die Verfügbarkeit einer Benutzer Zeile, indem es anderen Benutzern ermöglicht, einen eingehenden Anruf zu beantworten, indem Sie eine Gruppennummer für die Anruf Abholung wählen. Wenn die Gruppenanruf Abholung bereitgestellt wird, kann die Anzahl der eingehenden Anrufe, die an die Voicemail weitergeleitet werden, erheblich reduziert werden, was besonders für Anrufe von Kunden nützlich ist, die sich außerhalb Ihrer Organisation befinden.

Das Feature für die Gruppenanruf Abholung ist insbesondere für Unternehmenseinheiten in offenen Office-Umgebungen konzipiert. Eingehende Anrufe stören nicht, da sie nur am vorgesehenen Zieltelefon klingeln. Andere Benutzer, die das Klingeln hören, können den Anruf dennoch annehmen, indem sie einfach die Gruppennummer wählen.

In Umgebungen, in denen sich Benutzer nicht in einer offenen Büroanordnung oder – trotz gemeinsamer Verantwortungsbereiche – an verschiedenen geografischen Standorten befinden, ist die Teamanruffunktion die am besten geeignete Lösung. Der Hauptunterschied zwischen Gruppenanruf Abholung und Teamanruf besteht darin, dass ein eingehender Anruf nur an dem vorgesehenen Ziel klingelt, aber jeder kann ihn trotzdem durch Wählen einer Gruppennummer beantworten. Bei einem Teamanruf klingeln die Telefone aller Gruppenmitglieder und jeder Benutzer im Team kann den Anruf annehmen. Ein weiterer Unterschied zwischen Gruppenanruf Abholung und Team Anruf besteht darin, dass die Abholung von Gruppen anrufen von einem Administrator über lync Server verwaltet wird. Mit Team Anruf verwalten Endbenutzer das Feature mithilfe des lync-Clients. Mit der Gruppenanruf-Abholung kann dieser Aspekt der Anrufverwaltung also zentralisiert werden.

Die Abholung von Gruppen anrufen basiert auf der Anwendung für den Anruf Park. Wenn Sie die Gruppenanruf Abholung bereitstellen, konfigurieren Sie die Orbit-Tabelle des Anruf Parks mit getrennten Bereichen von Durchwahlnummern, die als Gruppennummern für die Anruf Abholung festgelegt sind. Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Anrufannahmegruppe um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanruf Abholung bereitstellen, kann über einen oder mehrere Bereiche der Gruppennummern für die Anruf Abholung verfügen. Die Gruppennummern Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.

<div>


> [!NOTE]  
> Nummernkreise, die als Gruppenanruf-Abhol Nummern in der Orbit-Tabelle des Anruf Parks bezeichnet werden, können mithilfe der lync Server-Systemsteuerung nicht verwaltet oder angezeigt werden. Die einzige Möglichkeit, alle Nummernbereiche in der Orbit-Tabelle des Anruf Parks anzuzeigen, besteht darin, die lync Server-Verwaltungsshell zu verwenden. Ebenso besteht die einzige Möglichkeit zum Hinzufügen, ändern oder Entfernen von Gruppenanruf-Pickup-Nummern darin, die lync Server-Verwaltungsshell zu verwenden.



</div>

Nach dem Konfigurieren der Nummern für die Anrufannahmegruppe weisen Sie Benutzer einer Anrufannahmegruppe zu. Die Anrufe jedes Benutzers, der einer Anrufannahmegruppe zugewiesen ist, können von anderen Personen angenommen werden. Wenn ein Anruf an einen Benutzer eingeht, der einer Anrufannahmegruppe zugewiesen ist, kann ein beliebiger anderer Benutzer diesen Anruf annehmen, indem er manuell die Nummer für die Anrufannahmegruppe wählt. Der Benutzer, der den Anruf annimmt, muss kein Mitglied der Gruppe sein. Wenn ein Anruf von einem anderen Benutzer angenommen wird, wird eine Benachrichtigung an den Benutzer gesendet, dessen Nummer ursprünglich gewählt wurde.

<div>


> [!NOTE]  
> Ein Benutzer kann nur in einer Anrufannahmegruppe Mitglied sein.



</div>

<div>


> [!NOTE]  
> Obwohl jeder Benutzer in der lync Server-Bereitstellung einen Anruf an ein Mitglied der Anruf Abholungs Gruppe annehmen kann, muss die Person, die den Anruf annimmt, die richtige Anruf-Abhol Gruppennummer kennen, um zu wählen.



</div>

Wenn ein Benutzer zum Annehmen eines Anrufs die Nummer für die Anrufannahmegruppe wählt und mehrere Telefone in der Gruppe klingeln, nimmt der Benutzer den Anruf an, der bereits am längsten klingelt.

Einstellungen für gleichzeitig eingehende Anrufe funktionieren für Benutzer mit GroupCallPickup. Das bedeutet, dass ein Anruf an einen Benutzer, der eine Gruppenanruf-Abholung hat, für alle konfigurierten Ziele klingelt und ein anderer Benutzer den Anruf annehmen kann. Eine Ausnahme zu dieser Regel tritt auf, wenn der Benutzer gleichzeitig eingehende Anrufe so konfiguriert, dass sie an alle Teammitglieder eingehen.

Die Gruppenanruf Abholung kann nicht zur Beantwortung der folgenden Anrufarten verwendet werden:

  - Anrufe an eine Privatleitung

  - Anrufe von Kontakten, denen die private Beziehung „Freunde und Familie“ zugewiesen wurde
    
    <div>
    

    > [!TIP]  
    > Ein Benutzer, der Mitglied einer Anruf Abhol Gruppe ist, kann verhindern, dass bestimmte Anrufe über die Gruppenanruf Abholung abgerufen werden, indem der Kontakt als persönlicher Kontakt im lync-Client markiert wird. Zum Kennzeichnen eines Kontakts als persönlichen Kontakt legen Sie die private Beziehung für den Kontakt auf „Freunde und Familie“ fest. Alle eingehenden Anrufe von Kontakten mit der privaten Beziehung, die auf Freunde und Familie eingestellt sind, können mit der Gruppenanruf-Abholung nicht abgerufen werden.

    
    </div>

  - Videoteil von Audio-/Videoanrufen
    
    <div>
    

    > [!NOTE]  
    > Wenn ein Benutzer einen Audio-/Videoanruf annimmt, empfängt er nur den Audioteil. Der Anruf kann entweder vom Anrufer oder von der Person, die den Anruf annimmt, hochgestuft und damit der Videoteil hinzugefügt werden.

    
    </div>

  - Gleichzeitig eingehende Anrufe, die an Teamanrufmitglieder weitergeleitet werden

  - An einen Stellvertreter weitergeleitete Anrufe

  - An eine Antwortgruppe weitergeleitete Anrufe

Die folgenden Benutzertypen können nicht an der Gruppenanruf Abholung teilnehmen. Das heißt, Sie sollten nicht in eine Gruppenanruf-Abhol Gruppe aufgenommen werden, und Sie können keine Anrufe für Benutzer aufnehmen, die die Gruppenanruf Abholung aktiviert haben.

  - Benutzer, die online in einer Hybridbereitstellung gehostet sind

  - Benutzer, die nicht in einem lync Server 2013-Pool mit kumulativen Updates für lync Server 2013: Februar 2013 in einer lokalen Bereitstellung verwaltet werden

Wenn ein Anruf an ein Mitglied einer Anrufannahmegruppe nicht angenommen wird, wird der Anruf gemäß den Angaben in den Clienteinstellungen weitergeleitet. Das bedeutet, dass der Anruf an Voicemail oder wie in den Clienteinstellungen angegeben an ein anderes Zieltelefon weitergeleitet wird.

</div>

<span> </span>

</div>

</div>

</div>

