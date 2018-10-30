---
title: 'Lync Server 2013: Reduzieren von nicht angeforderten Chatnachrichten'
TOCTitle: Reduzieren von nicht angeforderten Chatnachrichten für Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn518335(v=OCS.15)
ms:contentKeyID: 60476349
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Reduzieren von nicht angeforderten Chatnachrichten für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-12-05_

Der intelligente Chatnachrichtenfilter trägt dazu bei, Ihre Microsoft Lync Server 2013-Bereitstellung mit minimaler Auswirkung auf die Benutzerfreundlichkeit vor den gängigsten Viren zu schützen. Der intelligente Chatnachrichtenfilter bietet Folgendes:

  - Verbesserte URL-Filterung

  - Verbesserte Filterung von Dateiübertragungen

Verwenden Sie den intelligenten Chatnachrichtenfilter, um Filter zu konfigurieren, die nicht angeforderte oder potenziell schädliche Chatnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall blockieren. Sie konfigurieren Filter, indem Sie die verwendeten Kriterien angeben, um zu bestimmen, was blockiert werden soll, beispielsweise Chatnachrichten, die Hyperlinks enthalten, und Dateien mit bestimmten Dateierweiterungen.

Vor dem Bereitstellen der Anwendung für intelligente Chatnachrichtenfilter sollten Sie verstehen, wie Filteroptionen auf Nachrichten angewendet werden, die von einem Server mit Lync Server 2013 an einen anderen Server weitergeleitet werden. Die Art der Anwendung von Filteroptionen ist konsistent. Dabei spielt es keine Rolle, ob die Server sich in einer einzigen Organisation oder in mehreren Organisationen befinden. Die Konsistenz betrifft die Art und Weise, wie benutzerdefinierte Hinweise und Warntexte in Nachrichten eingefügt und an Server gesendet werden.

Die empfohlene Filterungsoption ist, Chatnachtrichten mit Hyperlinks zuzulassen, aber vom intelligenten Chatnachrichtenfilter zu fordern, den Link zu deaktivieren, indem ein Unterstrich davor eingefügt wird. Wenn Sie diese Option auswählen, haben Sie die zusätzliche Option, eine Notiz an Benutzer zu verfassen, die zu Beginn jeder Chatnachricht angezeigt wird, die einen Hyperlink enthält.

Eine zweite Filterungsoption besteht darin, Chatnachrichten mit unveränderten Hyperlinks zuzulassen. Wenn Sie diese Option auswählen, haben Sie die zusätzliche Option (empfohlen), eine Warnung für Benutzer zu verfassen, die in jede Nachricht eingefügt wird.

Eine dritte Option besteht darin, alle Chatnachrichten zu blockieren, die Hyperlinks enthalten. Wenn Sie diese Option auswählen, sendet der Server eine Warnung an den Benutzer. Sie müssen diese Warnung schreiben.

