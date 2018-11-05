---
title: 'Lync Server 2013: VoIP-Komponenten der Front-End-Server'
TOCTitle: VoIP-Komponenten der Front-End-Server
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425812(v=OCS.15)
ms:contentKeyID: 49293587
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoIP-Komponenten der Front-End-Server für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Auf Front-End-Servern befinden sich die folgenden VoIP-Komponenten:

  - Übersetzungsdienst

  - Eingangsroutingkomponente

  - Ausgangsroutingkomponente

  - Routingkomponente für Exchange UM

  - Komponente für das clusterübergreifende Routing

  - [Vermittlungsserverkomponente in Lync Server 2013](lync-server-2013-mediation-server-component.md)

## Übersetzungsdienst

Der Übersetzungsdienst ist die Serverkomponente, die eine gewählte Nummer gemäß den vom Administrator definierten Normalisierungsregeln in das E.164-Format oder ein anderes Format übersetzt. Der Übersetzungsdienst kann in andere Formate als E.164 übersetzen, wenn in Ihrer Organisation ein privates Nummernsystem oder ein Gateway bzw. eine Nebenstellenanlage verwendet wird, das bzw. die E.164 nicht unterstützt.

## Eingangsroutingkomponente

Die Eingangsroutingkomponente verarbeitet eingehende Anrufe im Wesentlichen anhand der Einstellungen, die Benutzer auf ihren Enterprise-VoIP-Clients angeben. Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern vom Benutzer konfiguriert. Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen. Wenn die Anrufweiterleitung aktiviert ist, können die Benutzer angeben, ob unbeantwortete Anrufe an eine andere Nummer oder an einen Exchange UM-Server weitergeleitet werden sollen, der für die Bereitstellung einer Mailboxansage konfiguriert wurde. Die Eingangsroutingkomponente wird standardmäßig auf allen Standard Edition-Servern sowie auf Front-End-Servern installiert.

## Ausgangsroutingkomponente

Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter. Sie wendet (gemäß Definition in der VoIP-Richtlinie für den Benutzer) Anrufautorisierungsregeln auf Anrufer an und ermittelt das optimale PSTN-Gateway für das Routing der einzelnen Anrufe. Die Ausgangsroutingkomponente wird standardmäßig auf allen Standard Edition-Servern sowie auf Front-End-Servern installiert.

Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird.

## Routingkomponente für Exchange UM

Die Routingkomponente für Exchange UM ist für das Routing zwischen Lync Server und Servern mit Exchange Unified Messaging (UM)) zuständig, um Unified Messaging-Features in Lync Server zu integrieren.

Die Exchange UM-Routingkomponente sorgt außerdem für eine Voicemailumleitung über das Telefonfestnetz, wenn keine Exchange UM-Server zur Verfügung stehen. Wenn Sie über Enterprise-VoIP-Benutzer an Zweigstellenstandorten ohne ausfallsichere WAN-Verbindung mit einem zentralen Standort verfügen, bietet die am Zweigstellenstandort bereitgestellte Survivable Branch-Anwendung während eines WAN-Ausfalls grundlegende VoIP-Funktionen für die Zweigstellenbenutzer. Bei einem Ausfall der WAN-Verbindung sorgt die Survivable Branch-Anwendung für Folgendes:

  - Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet

  - Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen

  - Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist

In Bezug auf die Aktivierung der Voicemailumleitung wird empfohlen, dass der Exchange-Administrator die automatische Exchange UM-Telefonzentrale nur zum Akzeptieren von Nachrichten konfiguriert.

Ausführliche Informationen zu diesen Features finden Sie unter [Planen der Integration von Exchange Unified Messaging in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) bzw. [Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md).

## Komponente für das clusterübergreifende Routing

Diese Komponente sorgt für das Routing von Anrufen beim primären Registrierungspool des Anrufempfängers. Wenn dieser Pool nicht verfügbar ist, leitet die Komponente den Anruf an den Sicherungsregistrierungspool des Anrufempfängers weiter. Wenn keiner der beiden Pools über das IP-Netzwerk erreicht werden kann, leitet die Komponente für das clusterübergreifende Routing den Anruf über das Telefonfestnetz an die Rufnummer des Benutzers um.

## Andere für VoIP erforderliche Front-End-Serverkomponenten

Zu den weiteren Komponenten, die sich auf dem Front-End-Server oder dem Director befinden und grundlegende Unterstützung für VoIP bieten, jedoch selbst keine VoIP-Komponenten darstellen, gehören die folgenden:

  - **Benutzerdienste.** Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu. Mithilfe dieser Informationen verteilt die Eingangsroutingkomponente den Anruf an die registrierten SIP-Endpunkte dieses Benutzers. Die Benutzerdienste stellen eine Hauptkomponente auf allen Front-End-Servern und Directors dar.

  - **Benutzerreplikationsdienst.** Der Benutzerreplikationsdienst extrahiert Benutzerrufnummern aus Active Directory-Domänendienste und schreibt sie in Tabellen der RTC-Datenbank. Dort stehen sie für die Benutzerdienste und den Adressbuchserver zur Verfügung. Der Benutzerreplikationsdienst ist eine Hauptkomponente auf allen Front-End-Servern.

  - **Adressbuchserver.** Stellt Informationen aus der globalen Adressliste der Active Directory-Domänendienste für Lync Server-Clients bereit. Er ruft darüber hinaus Benutzer- und Kontaktinformationen aus der RTC-Datenbank ab, schreibt die Informationen in die Adressbuchdateien und speichert die Dateien anschließend in einem freigegebenen Ordner, sodass sie von Lync-Clients heruntergeladen werden können. Der Adressbuchserver schreibt die Informationen in die RTCAb-Datenbank, die vom Adressbuch-Webabfragedienst dazu verwendet wird, Suchabfragen von Benutzern von Microsoft Lync 2010 Mobile zu beantworten. Optional normalisiert der Adressbuchserver die Rufnummern von Unternehmensbenutzern, die in die RTC-Datenbank geschrieben werden, um Benutzerkontakte in Lync bereitzustellen. Der Adressbuchserver wird standardmäßig auf jedem Front-End-Server installiert. Der Adressbuch-Webabfragedienst wird standardmäßig mit den Webdiensten auf jedem Front-End-Server installiert.

