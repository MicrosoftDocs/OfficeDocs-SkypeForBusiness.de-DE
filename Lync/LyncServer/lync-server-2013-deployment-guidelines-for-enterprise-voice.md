---
title: 'Lync Server 2013: Richtlinien für die Enterprise-VoIP-Bereitstellung'
TOCTitle: Richtlinien für die Enterprise-VoIP-Bereitstellung
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398694(v=OCS.15)
ms:contentKeyID: 49294671
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Richtlinien für die Enterprise-VoIP-Bereitstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In diesem Thema werden die Voraussetzungen und andere Richtlinien beschrieben, die Sie bei der Bereitstellungsplanung für Lync Server 2013 und eine Enterprise-VoIP-Arbeitsauslastung berücksichtigen sollten.

## Voraussetzungen für die Bereitstellung

Für ein optimales Ergebnis stellen Sie beim Bereitstellen von Enterprise-VoIP sicher, dass IT-Infrastruktur, Netzwerk und Systeme die folgenden Anforderungen erfüllen:

  - Lync Server 2013 Standard Edition oder Enterprise Edition ist im Netzwerk installiert und wird ausgeführt.

  - Alle Edgeserver und Reverseproxys wurden in Ihrem Umkreisnetzwerk bereitgestellt und sind betriebsbereit - die Edgeserver mit Zugriffs-Edgedienst, A/V-Edgedienst, Webkonferenz-Edgedienst und ein Reverseproxy eingeschlossen.

  - Es wurden Benutzer für Lync Server erstellt und aktiviert.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) oder mit dem neuesten Service Pack oder Microsoft Exchange Server 2010 wird installiert. Mindestens eine dieser Versionen ist für die Integration von Exchange Unified Messaging (UM) mit Lync Server und zur Bereitstellung von detaillierten Benachrichtigungen und Anrufprotokollinformationen für die Clientendpunkte erforderlich.

  - Für jeden Benutzer, für den Enterprise-VoIP aktiviert werden soll, wurde eine eindeutige primäre Rufnummer festgelegt, normalisiert und in das Attribut **msRTCSIP-line** kopiert.
    

    > [!NOTE]
    > Lync Server unterstützt E.164-Nummern und Nicht-DID-Nummern (Direct Inward Dialing). Nicht-DID-Nummern können im Format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> oder als Ziffernfolge dargestellt werden. Dabei gilt die Anforderung, dass die private Durchwahl im Unternehmen eindeutig ist. Die private Nummer&nbsp;1001 kann z.&nbsp;B. als <STRONG>+1425550100;ext=1001</STRONG> oder als <STRONG>1001</STRONG> dargestellt werden. Bei Darstellung als <STRONG>1001</STRONG> wird vorausgesetzt, dass die private Nummer im Unternehmen eindeutig ist.



  - Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

  - Mindestens Office Communicator 2007 wurde erfolgreich bereitgestellt. Zur Verwendung der neuen Funktionen in dieser Version wurde Lync 2013 bereitgestellt.

  - Es wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter eine Managed Key-Infrastruktur (MKI) bereitgestellt und konfiguriert.

  - Für jeden Computer, auf dem Sie einen Vermittlungsserver installieren, gilt Folgendes:
    
      - Ein Mitgliedsserver einer Domäne, der für Active Directory-Domänendienste vorbereitet ist. Ausführliche Informationen zum Vorbereiten von Active Directory-Domänendienste finden Sie unter [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.
    
      - Es muss eines der folgenden Betriebssysteme ausgeführt werden:
        
          - Die 64-Bit-Version von Windows Server 2008 Standard
        
          - Die 64-Bit-Version von Windows Server 2008 Enterprise

  - Wenn die Verbindung zum Telefonfestnetz (Public Switched Telephone Network, PSTN) oder zu einer Nebenstellenanlage (Private Branch Exchange, PBX) per TDM-Verbindung (Time Division Multiplexing) erfolgt, stehen für die Bereitstellung ein oder mehrere PSTN-Gateways zur Verfügung. (Falls die Verbindung über einen SIP-Trunk hergestellt wird, ist kein PSTN-Gateway erforderlich.)

## Stromausfall, Ausfall des Netzwerks oder des Telefondiensts

Sollte es an Ihrem Standort zu einem Ausfall, einer Unterbrechung oder einer Störung der Stromversorgung, des Netzwerks oder des Telefondiensts kommen, sind Lync Server-Funktionen wie VoIP, Sofortnachrichten oder Anwesenheit sowie die mit Lync Server verbundenen Geräte möglicherweise nicht einwandfrei funktionsfähig.

## Abhängigkeit von Enterprise-VoIP von der Verfügbarkeit des Servers sowie der Funktionsfähigkeit des VoIP-Client und der Hardware

Die VoIP-Kommunikation mit Lync Server hängt von der Verfügbarkeit der Serversoftware sowie der ordnungsgemäßen Funktionsweise der VoIP-Clients bzw. der mit der Serversoftware verbundenen Telefone ab.

## Alternativer Zugriff auf Notrufdienste

Es wird empfohlen, an Standorten, an denen ein VoIP-Client installiert ist (z. B. auf einem PC mit Lync-Client oder auf einem Gerät mit Lync Phone Edition), den Benutzern die Möglichkeit zu geben, Notrufdienste auch dann weiterhin anrufen zu können, wenn es zu einem Stromausfall kommt oder Lync Server, Lync bzw. die Geräte mit der Lync Phone Edition aufgrund von Problemen mit dem Netzwerk oder dem Telefondienst oder anderen Störungen nicht funktionsfähig sind. Optionen für einen solchen alternativen Zugriff auf Notrufdienste sind beispielsweise ein Telefonfestnetz oder ein Mobiltelefon.

## Notruf und Telefonsysteme mit mehreren Leitungen

Die Verwendung von Mehrleitungstelefonsystemen (MLTS) unterliegt eventuell gesetzlichen Bestimmungen, die bei einem Notruf die Angabe der Rufnummer, der Durchwahl und/oder des physischen Standorts des Anrufers erfordern. In dieser Version kann Lync Server so konfiguriert werden, dass der physische Standort eines Anrufers an den Anbieter für die Notrufunterstützung übermittelt wird (siehe [Planen von Notrufdiensten (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)). Die Einhaltung gesetzlicher Bestimmungen für Mehrleitungstelefonsysteme obliegt alleine den Käufern von Lync Server, Lync-Clients und Lync Phone Edition-Geräten.

