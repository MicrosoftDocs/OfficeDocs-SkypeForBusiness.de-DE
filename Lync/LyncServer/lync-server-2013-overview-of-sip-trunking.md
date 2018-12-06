---
title: 'Lync Server 2013: Übersicht über SIP-Trunking'
TOCTitle: Übersicht über SIP-Trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398285(v=OCS.15)
ms:contentKeyID: 49293396
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über SIP-Trunking in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Die Bereitstellung von SIP-Trunking kann die Telefonkommunikation in Ihrer Organisation deutlich vereinfachen und stellt gleichzeitig eine Vorbereitung auf die neuesten Funktionen für die Echtzeitkommunikation dar. Einer der Hauptvorteile beim SIP-Trunking besteht darin, dass Sie PSTN-Verbindungen (Public Switched Telephone Network, Telefonfestnetz) an einem zentralen Standort in Ihrer Organisation konsolidieren können - im Gegensatz zum Vorgänger, dem Legacy-TDM (Time Division Multiplexing)-Trunking, das in der Regel einen separaten Trunk für jeden Zweigstellenstandort erfordert.

## SIP-Trunking in Lync Server

Die SIP-Trunking-Funktionen von Lync Server 2013 ermöglichen Folgendes:

  - Ein Unternehmensbenutzer, der sich innerhalb oder außerhalb der Unternehmensfirewall befindet, kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer tätigen, die im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters terminiert wird.

  - Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID (Direct Inward Dialing)-Nummer wählt, die dem Unternehmensbenutzer zugeordnet ist.

## Kosteneinsparung

Die mit dem SIP-Trunking verbundene Kosteneinsparung kann erheblich sein:

  - Die Kosten für Ferngespräche sind bei Verwendung eines SIP-Trunks in der Regel deutlich niedriger.

  - Sie können die Verwaltungskosten senken und die Komplexität der Bereitstellung verringern.

  - Gebühren für Basisanschlüsse (Basic Rate Interface, BRI) und Primärmultiplexanschlüsse (Primary Rate Interface, PRI) entfallen, wenn Sie eine deutlich günstigere Direktverbindung zwischen SIP-Trunk und Ihrem Anbieter von Internettelefoniediensten (ISTP) konfigurieren. Beim TDM-Trunking rechnen Dienstanbieter Anrufe pro Minute ab. Die Kosten für das SIP-Trunking können auf der Bandbreitennutzung basieren, die Sie in kleineren, wirtschaftlicheren Einheiten erwerben können. (Die tatsächlichen Kosten richten sich nach dem Servicemodell des jeweiligen Anbieters von Internettelefoniediensten (ITSP).)

## SIP-Trunking im Vergleich zum Hosting eines PSTN-Gateways oder einer IP-Nebenstellenanlage

Da SIP-Trunks eine direkte Verbindung mit dem Dienstanbieter herstellen, entfallen Ihre PSTN-Gateways und die damit verbundenen Verwaltungskosten sowie die Komplexität dieser Lösung. Die Verwendung von SIP-Trunks kann durch einen geringeren Wartungs- und Verwaltungsaufwand zu einer erheblichen Kosteneinsparung beitragen.

## Erweiterte VoIP-Dienste

VoIP-Funktionen sind häufig die wichtigste Motivation für die Bereitstellung von SIP-Trunking, die VoIP-Unterstützung stellt jedoch nur den ersten Schritt dar. Mit dem SIP-Trunking können Sie die VoIP-Funktionen erweitern und Lync Server 2013 zur Bereitstellung vielfältiger Dienste nutzen. Beispiel:

  - Die erweiterte Anwesenheitserkennung für Geräte ohne Lync Server 2013 ermöglicht eine bessere Integration für Mobiltelefone, sodass Sie sehen können, wenn ein Benutzer ein Gespräch über ein Mobiltelefon führt.

  - E9-1-1-Notrufdienste ermöglichen es der Rettungsleitstelle, die den Notruf entgegennimmt, basierend auf der Telefonnummer den geografischen Standort des Anrufers zu ermitteln.


> [!NOTE]
> Erkundigen Sie sich bei Ihrem ITSP, welche Dienste unterstützt werden und für Ihre Organisation aktiviert werden können.


