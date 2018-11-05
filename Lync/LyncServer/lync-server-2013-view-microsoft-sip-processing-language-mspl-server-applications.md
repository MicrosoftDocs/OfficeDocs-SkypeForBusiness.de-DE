---
title: 'Lync Server 2013: Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language)'
TOCTitle: Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language)
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182575(v=OCS.15)
ms:contentKeyID: 49295186
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-09-26_

Eine MSPL-Serveranwendung (Microsoft SIP Processing Language) ist eine Nur-Skript-Anwendung, die anstelle der Microsoft Lync 2010-API eine Skriptsprache verwendet. MSPL ermöglicht eine genauere Steuerung des Filter- und Proxyverhaltens und bietet eine Funktion zum Weiterleiten bestimmter Nachrichten an transaktionsbasierte SIP-Anwendungen. MSPL wird insbesondere zum Filtern und Weiterleiten von SIP-Nachrichten verwendet. MSPL-Anwendungen werden im selben Prozess wie das UserServices-Modul ausgeführt, während auf der Lync 2010-API basierende Programme in einem eigenen Prozess ausgeführt werden.

Sie können auf der Seite **Serveranwendung** in der Gruppe **Topologie** der Lync Server-Systemsteuerung eine Liste der MSPL-Serveranwendungen anzeigen, die auf den Front-End-Servern in Ihrer Lync Server 2013-Umgebung ausgeführt werden. Die Liste zeigt die für jeden Pool verfügbaren Skripts und gibt an, ob diese aktiviert oder kritisch sind. Die Skripts werden in der Reihenfolge ihrer Auflistung ausgeführt.

Die folgenden Skripts sind verfügbar:

  - ClientVersionFilter ermöglicht Administratoren, die von einem Pool unterstützte Version der Clients anzugeben. Mit dem Clientversionsfilter kann die Clientversion überprüft und dann entweder die Anmeldung des Clients verhindert oder dem Benutzer eine Meldung angezeigt werden, dass eine nicht unterstützte Clientversion verwendet wird. Der Clientversionsfilter kann auch so konfiguriert werden, dass dem Benutzer eine Meldung mit der URL der aktuellen herunterladbaren Version des Clients angezeigt wird.

  - TranslationService wandelt eine von einem Benutzer gewählte Nummer entsprechend den vom Administrator festgelegten Normalisierungsregeln in eine E.164-Nummer um. Ausführliche Informationen finden Sie unter [Übersetzungsregeln in Lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation erzwingt Verbundvalidierung auf Mandantenebene für Nachrichten zwischen Mandanten und aus externen Bereitstellungen eingehende Nachrichten.

  - Bei UserServices handelt es sich um die SIP-Registrierungs-, Anwesenheits- und Konferenzkomponente eines Front-End-Servers. Dieses Skript stellt integrierte Sofortnachrichten-, Anwesenheits- und Konferenzfunktionen auf Basis des SIP-Proxys bereit.

  - InterClusterRouting sorgt für das Routing von Anrufen beim primären Registrierungspool des Anrufempfängers. Ausführliche Informationen finden Sie unter [VoIP-Komponenten der Front-End-Server für Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (Intelligent IM Filter) blockiert Nachrichten, die anklickbare URLs enthalten oder versuchen, eine Dateiübertragung zu initiieren. IIMFilter prüft auch die Clientversion im Namen des Servers. IIMFilter betrifft Dateiübertragungen, die über Lync Server oder Communicator initiiert wurden. Standardmäßig werden anklickbare Links deaktiviert, indem ein Unterstrich vor dem ersten Zeichen des Links hinzugefügt wird. Ein Administrator kann dieses Verhalten ändern, damit der Link blockiert wird. In diesem Fall werden Nachrichten, die anklickbare URLs enthalten oder versuchen, eine Dateiübertragung zu initiieren, vom Server daran gehindert, ihr Ziel zu erreichen. IIMFilter wird auf allen Servern mit Lync Server außer Proxyservern und Archivierungsservern installiert.

  - UserPinService wird verwendet, um die persönlichen Identifikationsnummern (PINs) für Einwahlkonferenzen zu überprüfen.

  - DefaultRouting ist die Standardroutinganwendung für Lync Server-Server. Diese Anwendung ist standardmäßig aktiviert. Die Routinganwendung wird auf allen Standard Edition- und Enterprise Edition-Servern installiert.

  - Mit ExumRouting werden Anrufe von Exchange Server Unified Messaging (UM) weitergeleitet. ExumRouting ermittelt bei Eingang einer neuen Voicemailnachricht den geeigneten Exchange UM-Server zum Weiterleiten des Anrufs. Mit ExumRouting werden zudem einige weitere Integrationsaspekte von Exchange UM behandelt, u. a. die Weiterleitung an eine automatische Telefonzentrale und der Teilnehmerzugriff.

  - OutboundRouting ermittelt das Gateway, das einen Anruf gemäß der gewählten Nummer und der Wählberechtigungen des Benutzers an eine Telefonnummer weiterleitet. OutboundRouting leitet Anrufe auch um, wenn ein Gateway einen Anruf nicht verarbeiten kann.

  - QoEAgent empfängt über SIP SERVICE-Anforderungen QoE-Datenberichte (Quality of Experience) von Endpunkten und sendet die Daten unter Verwendung von HTTP POST an die Zielwarteschlange auf dem Monitoring Server oder an Empfänger eines Drittanbieters. Ausführliche Informationen finden Sie unter [Bereitstellen des Monitoring Servers](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation erzwingt Verbundvalidierung auf Mandantenebene für Nachrichten an eine gezielte externe Bereitstellung.

  - AcpRouting leitet die für den Audiokonferenzanbieter bestimmten INVITE-Anforderungen an das Gateway des Audiokonferenzanbieters weiter.

Auf Edgeservern werden die folgenden Skripts ausgeführt:

  - IIMFilter

  - OptionsHandler beantwortet eingehende OPTIONS-Anforderungen mit **200 OK** , wenn die Anforderung für den aktuellen Server bestimmt ist. Dies wird für die Topologievalidierung verwendet.

## Siehe auch

#### Aufgaben

[Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language)](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Markieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)

