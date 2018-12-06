---
title: 'Lync Server 2013: Erstellen von Agent-Gruppen für Reaktionsgruppen'
TOCTitle: Erstellen von Agent-Gruppen für Reaktionsgruppen
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520969(v=OCS.15)
ms:contentKeyID: 49293509
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Außerdem geben Sie zusätzliche Gruppeneinstellungen (beispielsweise die Routingmethode) an und legen fest, ob sich ein Agent bei der Gruppe an- und abmelden muss.

Ein Agent, der sich bei der Gruppe an- und abmelden muss (unabhängig vom An- und Abmelden bei Lync Server) wird als *formeller Agent* bezeichnet. Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können. Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen. Formelle Agents melden sich bei ihren Gruppen an und ab, indem sie in Lync 2013 auf eine Menüoption klicken, um Windows Internet Explorer zu öffnen und eine Webseitenkonsole anzuzeigen.

Ein Agent, der sich nicht bei einer Gruppe anmeldet oder abmeldet, wird als *informeller Agent* bezeichnet. Informelle Agents werden automatisch bei der Gruppe angemeldet, sobald sie sich bei Lync Server anmelden. Sie haben nicht die Möglichkeit, sich von der Gruppe abzumelden.


> [!NOTE]
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von der lokalen Verwendung zur Onlinebereitstellung wechselt, werden die Anrufe der Reaktionsgruppe nicht mehr an diesen Agent weitergeleitet.



## In diesem Abschnitt

[Erstellen oder Ändern einer Agent-Gruppe in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

