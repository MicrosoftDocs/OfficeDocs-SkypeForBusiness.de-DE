---
title: Konfigurieren von Clients von Lync Server 2013 für die Verwendung mit Office Web Apps Server
TOCTitle: Konfigurieren von Clients von Lync Server 2013 für die Verwendung mit Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205339(v=OCS.15)
ms:contentKeyID: 49295720
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Clients von Lync Server 2013 für die Verwendung mit Office Web Apps Server

 

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Wenn Benutzern das volle Funktionsspektrum von Office Web App Server zur Verfügung stehen soll, sollten Sie diese Benutzer auf Microsoft Lync 2013 upgraden. Nur Benutzer von Lync 2013 können beispielsweise PowerPoint-Folien unabhängig von der eigentlichen PowerPoint-Präsentation anzeigen. (Diese Benutzer können jede Folie der Präsentation betrachten, ohne in irgendeiner Weise die eigentliche Präsentation zu beeinflussen.) Benutzer, die Lync 2013 nicht verwenden, können zwar an Onlinekonferenzen teilnehmen und die PowerPoint-Präsentation anzeigen. Sie können jedoch die Folien nicht separat anzeigen, und sie sehen auch keine Folienübergänge und keine eingebetteten Videos.

Beachten Sie, dass diese Funktionen für Benutzer von Lync 2013 immer verfügbar sind. Dies gilt auch, wenn der PowerPoint-Referent Microsoft Lync 2010 verwendet. Falls eine PowerPoint-Präsentation von einem Benutzer gehostet wird, der Lync 2010 verwendet, hält Lync Server 2013 Absprache mit Office Web Apps Server, um sicherzustellen, dass Benutzer von Lync 2013 die Office Web Apps Server-Version dieser Präsentation zu sehen bekommen. Office Web Apps Server bietet Benutzern, die andere Clients als Lync 2013 ausführen, keine PowerPoint-Dienste an. Stattdessen stellen diese Benutzer eine Verbindung mit dem Konferenzserverdienst her und zeigen PowerPoint-Präsentationen genau so an wie das in Microsoft Lync Server 2010 der Fall war. Dies bedeutet auch, dass diese Benutzer nur Zugriff auf die begrenzten Funktionen von Lync Server 2010 haben.

Für Office Web Apps Server ist zwar keine Clientkonfiguration erforderlich (außer dem Upgraden der Benutzer auf Lync 2013), aber es wird empfohlen, dass die Konferenzteilnehmer auf Internet Explorer 9 upgraden. Der Zugriff auf Konferenzen ist zwar auch mit Internet Explorer 8 möglich, aber es gibt einige Einschränkungen bezüglich der Verwendung dieses Webbrowsers. Beispielsweise können Benutzer von Internet Explorer 8 für das PowerPoint-Freigabefenster keine benutzerdefinierte Größe festlegen. Stattdessen müssen Sie einen von drei vordefinierten Freigabefenstergrößen verwenden. Entsprechend können Benutzer von Internet Explorer 8 keine Mediendateien wiedergeben.

