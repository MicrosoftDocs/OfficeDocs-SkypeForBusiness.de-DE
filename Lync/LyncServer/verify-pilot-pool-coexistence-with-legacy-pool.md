---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
TOCTitle: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205420(v=OCS.15)
ms:contentKeyID: 49296015
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Nach dem Bereitstellen des Pilotpools müssen Sie die Koexistenz der beiden Pools verifizieren, indem Sie mithilfe der Verwaltungstools die Poolinformationen abrufen. Für die Lync Server 2013-Pools und die Pools der Vorgängerversion müssen Sie die Systemsteuerung für Lync Server 2013 und die Tools des Topologie-Generators verwenden.

## Sicherstellen, dass die Lync Server 2013-Dienste gestartet wurden

1.  Navigieren Sie auf dem Lync Server 2013-Front-End-Server zum Applet "Dienste" in "Verwaltung".

2.  Stellen Sie sicher, dass auf dem Front-End-Server die folgenden Dienste ausgeführt werden:

**Lync Server 2013-Dienste**

![Liste der gestarteten Lync Server-Dienste](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Liste der gestarteten Lync Server-Dienste")

## Öffnen der Systemsteuerung für Lync Server 2013

Öffnen Sie auf dem Front-End-Server in der Lync Server 2013-Bereitstellung die Systemsteuerung für Lync Server 2013, und wählen Sie den Lync Server 2010-Pool aus. Wiederholen Sie dieses Verfahren, um den Lync Server 2013-Pool zu öffnen.

**Öffnen der Lync Server 2013-Systemsteuerung**

![URL auswählen (Dialogfeld)](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "URL auswählen (Dialogfeld)")


> [!IMPORTANT]
> In Lync Server 2013 müssen Sie Silverlight auf Silverlight, Version 5, upgraden, bevor Sie die Lync Server-Systemsteuerung verwenden.



Diese Topologie enthält nun Lync Server 2010- und Lync Server 2013-Serverrollen.

**Topologieseite in der Lync Server 2013-Systemsteuerung**

![Lync Server-Systemsteuerung – Topologie (Seite)](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server-Systemsteuerung – Topologie (Seite)")

## Versuchen Sie nicht, die Topologie im Lync Server 2010-Topologie-Generator zu öffnen.

Wenn Sie versuchen, die Topologie mithilfe des Lync Server 2010-Topologie-Generators zu öffnen, erhalten Sie den unten angegebenen Fehler. Die Topologie kann nur mit dem Lync Server 2013-Topologie-Generator angezeigt werden. Der Lync Server 2013-Topologie-Generator muss zum Erstellen von Pools sowohl für Lync Server 2013 als auch für Lync Server 2010 verwendet werden.

**Fehlermeldung im Lync Server 2010-Topologie-Generator**

![Lync Server-Topologie-Generator – MMC-Snap-In-Fehler](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server-Topologie-Generator – MMC-Snap-In-Fehler")

