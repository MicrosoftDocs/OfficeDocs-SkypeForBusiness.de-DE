---
title: 'Lync Server 2013: SIP-Trunking'
TOCTitle: SIP-Trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398619(v=OCS.15)
ms:contentKeyID: 49294524
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIP-Trunking in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-08-13_

SIP (Session Initiation Protocol) wird zum Initiieren und Verwalten von VoIP-Kommunikationssitzungen (Voice over IP) für grundlegende Telefondienste und zusätzliche Echtzeitkommunikationsdienste wie Instant Messaging, Konferenzfunktionen, Anwesenheitserkennung und Multimediafunktionen verwendet. Dieser Abschnitt umfasst Planungsinformationen für die Implementierung von *SIP-Trunks* , eine Art von SIP-Verbindung, die über die Grenzen Ihres lokalen Netzwerks hinausgeht.

## Was ist SIP-Trunking?

Bei einem SIP-Trunk handelt es sich um eine IP-Verbindung für die SIP-Kommunikation zwischen Ihrer Organisation und einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP), die über Ihre Firewall hinausgeht. Ein SIP-Trunk wird typischerweise verwendet, um den zentralen Standort Ihrer Organisation mit einem ITSP zu verbinden. In einigen Fällen können Sie das SIP-Trunking auch zum Verbinden einer Zweigstelle mit einem ITSP nutzen.

## SIP-Trunks im Vergleich zu direkten SIP-Verbindungen

Der Begriff *Trunk* wurde aus der leitungsvermittelten Technologie abgeleitet. Er bezieht sich auf eine dedizierte physische Leitung zur Verbindung von Telefonvermittlungsanlagen. Wie die Vorgängertechnologie, TDM-Trunks (Time Division Multiplexing), sind SIP-Trunks Verbindungen zwischen zwei separaten SIP-Netzwerken, dem Lync Server 2013-Unternehmen und dem ITSP. Im Gegensatz zu leitungsvermittelten Trunks handelt es sich bei SIP-Trunks um virtuelle Verbindungen, die über jeden der unterstützten Typen von SIP-Trunkingverbindungen hergestellt werden können. Ausführliche Informationen zu den unterstützten Verbindungstypen finden Sie unter [Implementierung von SIP-Trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

Bei direkten SIP-Verbindungen hingegen handelt es sich um SIP-Verbindungen, die nicht über die Grenzen des lokalen Netzwerks hinausgehen (das heißt, es wird eine Verbindung mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) oder einer Nebenstellenanlage (Private Branch Exchange, PBX) innerhalb des internen Netzwerks hergestellt). Ausführliche Informationen zur Verwendung von direkten SIP-Verbindungen mit Lync Server 2013 finden Sie unter [Direkte SIP-Verbindungen in Lync Server 2013](lync-server-2013-direct-sip-connections.md).

## In diesem Abschnitt

  - [Übersicht über SIP-Trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Implementierung von SIP-Trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Komponenten und Topologien für das SIP-Trunking in Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [SIP-Trunking für Zweigstellenstandorte in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Prüfliste für die Bereitstellung von SIP-Trunks für Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

