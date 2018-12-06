---
title: Verwalten von Agentgruppen für Reaktionsgruppen
TOCTitle: Verwalten von Agentgruppen für Reaktionsgruppen
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520976(v=OCS.15)
ms:contentKeyID: 49293653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Agentgruppen für Reaktionsgruppen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Eine Agentgruppe besteht aus einer Gruppe von Personen, die für die Entgegennahme von Reaktionsgruppenanrufen zuständig sind. Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Sie geben an, welche zusätzlichen Gruppeneinstellungen verwendet werden sollen und ob sich ein Agent bei der Gruppe an- und abmelden muss.


> [!NOTE]
> Benutzer müssen für Enterprise-VoIP aktiviert sein, damit sie Agentgruppen hinzugefügt werden können. Ausführliche Informationen zur Aktivierung eines Benutzers für Enterprise-VoIP finden Sie unter <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013</A>.




> [!NOTE]
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.



Ein Agent, der sich bei der Gruppe an- und abmelden muss (unabhängig vom An- und Abmelden bei Lync Server) wird als *formeller Agent* bezeichnet. Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können. Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen. Formelle Agents melden sich bei ihren Gruppen an und ab, indem sie in Lync 2013 auf eine Menüoption klicken, um Windows Internet Explorer zu öffnen und eine Webseitenkonsole anzuzeigen.

Ein Agent, der sich nicht bei einer Gruppe anmeldet oder abmeldet, wird als *informeller Agent* bezeichnet. Informelle Agents werden automatisch bei der Gruppe angemeldet, sobald sie sich bei Lync Server anmelden. Sie haben nicht die Möglichkeit, sich von der Gruppe abzumelden.


> [!IMPORTANT]
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach "RGS-Anwesenheitsmonitor"-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch "RGS-Anwesenheitsmonitor" nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.



## In diesem Abschnitt

  - [Erstellen oder Ändern einer Agent-Gruppe in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Löschen einer Agentgruppe](lync-server-2013-delete-an-agent-group.md)

