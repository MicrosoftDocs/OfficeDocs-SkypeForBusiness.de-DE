---
title: 'Lync Server 2013: Unterstützung von Funktionen für öffentlichen Chat'
TOCTitle: Unterstützung von Funktionen für öffentlichen Chat
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204732(v=OCS.15)
ms:contentKeyID: 49293384
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung von Funktionen für öffentlichen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Lync Server 2013 unterstützt die Verwendung von Verbindungen mit lizenzierten öffentlichen Instant Messaging-Diensten sowie die Verwendung von XMPP (eXtensible Messaging and Presence Protocol) zum Implementieren eines speziellen Verbundtyps, der einem Lync Server den Zugriff auf konfigurierte XMPP-Domänenpartner mithilfe des Lync 2013-Clients ermöglicht.

## Unterstützung öffentlicher Instant\_Messaging-Dienste

Derzeit unterstützte Partner für Verbindungen mit öffentlichen Instant Messaging-Diensten:

  - America Online

  - Windows Live

  - Yahoo\!

Für die Kommunikation mit Windows Live-Benutzern unterstützt Lync Server 2013 Peer-zu-Peer-Chatnachrichten sowie Audio- und Videoanrufe. Für die Kommunikation mit AOL und Yahoo\! unterstützt Lync Server 2013 Peer-zu-Peer-Chatnachrichten. Möglicherweise ist eine separate Lizenz erforderlich.


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



## Unterstützung des XMPP-Verbunds

Der XMPP-Verbund unterstützt die Kommunikation von Lync-Benutzern mit konfigurierten XMPP-Domänenbenutzern, die einen öffentlichen Anbieter wie GTalk nutzen. Die Kommunikation mit diesen Benutzern kann Folgendes beinhalten:

  - Peer-zu-Peer-Chatnachrichten und Anwesenheit

  - Erstellung von XMPP-Verbundkontakten im Lync-Client

