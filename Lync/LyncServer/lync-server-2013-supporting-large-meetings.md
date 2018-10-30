---
title: Unterstützen von großen Besprechungen mithilfe von Lync Server 2013
TOCTitle: Unterstützen von großen Besprechungen mithilfe von Lync Server 2013
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204894(v=OCS.15)
ms:contentKeyID: 49293985
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützen von großen Besprechungen mithilfe von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Bei großen Besprechungen findet das im vorangehenden Abschnitt beschriebene Testmodell keine Anwendung. Große Besprechungen weisen eigene spezifische Merkmale auf:

  - Das Besprechungsformat entspricht einem 1:n-Format.

  - Einer oder wenige Benutzer fungieren als Referenten, und alle anderen Benutzer sind Teilnehmer.

  - Die Freigabe von PowerPoint-Präsentationen stellt die Hauptaktivität hinsichtlich der Datenzusammenarbeit dar.

  - Die Übertragung von Audiosignalen ist erforderlich, Videobilder können ebenfalls übertragen werden.

  - Eine bestimmte Person, bei der es sich i. d. R. um den Organisator der Besprechung oder um einen Assistenten handelt, richtet die Besprechung rechtzeitig im Voraus ein.

  - Spezielle Mitarbeiter (nicht die Referenten) führen durch die Besprechung, kümmern sich um das Herstellen von Verbindungen zu Onlinebesprechungen, stellen sicher, dass das Teilen von Audio-, Video- und Folieninhalten funktioniert, verwalten den Wartebereich und die Benutzerrollen, schalten Teilnehmer stumm bzw. heben deren Stummschaltung auf, nehmen Fragen entgegen und verwalten Aufzeichnungen nach Bedarf.

Die Unterstützung großer Besprechungen mit bis zu 1000 Teilnehmern macht es erforderlich, dass auch Probleme im Zusammenhang mit dem Hardwarefreigabemodell und dem Verzicht auf reservierte Ressourcen behandelt werden.

Um ausreichende Speicherressourcen sowie die erforderliche CPU-Leistung für Besprechungen mit bis zu 1000 Teilnehmern bereitstellen zu können, sollten auf dem Front-End-Server, der als Host fungiert, keine anderen Sofortnachrichten-, Anwesenheits- oder Enterprise-VoIP-Arbeitslasten verarbeitet werden. Auch auf das Hosten anderer Besprechungen sollte unabhängig von ihrer Größe verzichtet werden. Dies bedeutet, dass für das Hosten von Besprechungen mit bis zu 1000 Teilnehmern ein separater Lync Server-Pool ausschließlich für diesen Zweck eingerichtet werden sollte.

In einem dedizierten Lync Server-Pool zum Hosten großer Besprechungen sollte auch jeweils immer nur eine große Besprechung mit bis zu 1000 Teilnehmern gehostet werden. Besprechungszeiten müssen daher im Voraus über einen Out-Of-Band-Planungsprozess reserviert werden, um dedizierten Support durch Front-End-Server zu gewährleisten. Wenn Sie mehrere große Besprechungen gleichzeitig hosten möchten, wird empfohlen, mehrere dedizierte Pools für große Besprechungen einzurichten.

Der Onlineanteil einer großen Besprechung sollte ferner durch eine eigene Person ausgeführt und überwacht werden. Dies kann – je nach Präferenz Ihrer Organisation – der Organisator der Besprechung, ein Stellvertreter oder Referent oder auch ein Mitglied des dedizierten Teams für große Besprechungen sein.

In den folgenden Abschnitten wird beschrieben, wie Sie einen dedizierten Pool für große Besprechungen implementieren. Dazu werden außerdem bewährte Methoden für die Unterstützung großer Besprechungen mit Lync Server 2013 vorgestellt.

## In diesem Abschnitt

  - [Einrichten der Unterstützung für große Besprechungen](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Verwalten von großen Besprechungen](lync-server-2013-managing-large-meetings.md)

