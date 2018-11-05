---
title: Überprüfen des Partnerverbunds und Remotezugriffs für externe Benutzer
TOCTitle: Überprüfen des Partnerverbunds und Remotezugriffs für externe Benutzer
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49890875
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen des Partnerverbunds und Remotezugriffs für externe Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2012-09-18_

Nach dem Übergang der Verbundroute zum Edgeserver von Lync Server 2013 sollten Sie einige Funktionstests ausführen, um zu überprüfen, ob sich der Verbund wie erwartet verhält. Tests für den Zugriff durch externe Benutzer sollten sämtliche Typen von externen Benutzern umfassen, die von Ihrer Organisation unterstützt werden. Dazu können die folgenden Typen zählen:

## Testen der Konnektivität externer Benutzer und des externen Zugriffs

  - Benutzer aus mindestens einer Partnerdomäne, ein interner Benutzer von Lync Server 2013 sowie ein Benutzer von Lync Server 2010. Testen Sie Sofortnachrichten, Anwesenheit. Audio/Video (A/V) und Desktopfreigabe.

  - Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für die die Bereitstellung abgeschlossen ist), die mit einem Benutzer von Lync Server 2013 und einem Benutzer von Lync Server 2010 kommunizieren.

  - Stellen Sie sicher, dass anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.

  - Ein in Lync Server 2010 verwalteter Benutzer unter Verwendung des Remotebenutzerzugriffs (Anmeldung an Lync Server 2010 von außerhalb des Intranets, doch ohne VPN) mit einem Benutzer von Lync Server 2013 und einem Benutzer von Lync Server 2010. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.

  - Ein in Lync Server 2013 verwalteter Benutzer unter Verwendung des Remotebenutzerzugriffs (Anmeldung an Lync Server 2013 von außerhalb des Intranets, doch ohne VPN) mit einem Benutzer von Lync Server 2013 und einem Benutzer von Lync Server 2010. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.

