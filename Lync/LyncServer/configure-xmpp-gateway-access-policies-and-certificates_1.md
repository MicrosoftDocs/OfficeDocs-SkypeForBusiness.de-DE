---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
TOCTitle: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49890945
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

 

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Ein XMPP-Partnerverbund definiert eine externe Bereitstellung auf der Basis des Protokolls "eXtensible Messaging and Presence Protocol" (XMPP). Eine XMPP-Konfiguration gibt Lync-Benutzern Zugriff auf XMPP-Domänenbenutzer über folgende Funktionen:

  - Instant Messaging und Anwesenheit - nur zwischen Personen

  - Erstellung von XMPP-Verbundkontakten im Lync-Client

Wenn Sie Richtlinien zur Unterstützung von XMPP-Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Partnerdomänen, jedoch nicht für Benutzer von SIP-Chatdienstanbietern (z. B. Windows Live) oder SIP-Partnerdomänen. Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Partnerdomäne, zu der die Benutzer Kontakte hinzufügen und mit der sie kommunizieren dürfen sollen. Sobald die Richtlinien eingerichtet sind, müssen Sie die XMPP-Gatewayzertifikate konfigurieren.


> [!NOTE]
> Um mit der Migration von XMPP-Gateways beginnen zu können, müssen Sie das Lync Server 2013-XMPP-Gateway bereitstellen und Zugriffsrichtlinien konfigurieren, um Benutzer für das Lync Server 2013-XMPP-Gateway zu aktivieren. Alle Benutzer müssen in die Lync Server 2013-Bereitstellung verschoben werden, bevor Sie diese Schritte durchführen. Ausführliche Informationen finden Sie unter <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Konfigurieren eines XMPP-Gateways in Lync Server 2013</A>.



## Konfigurieren einer Richtlinie für den externen Zugriff, um Benutzer für das Lync Server 2013-XMPP-Gateway zu aktivieren

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie auf der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Richtlinie für den externen Zugriff** .

3.  Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie** .

4.  Geben Sie einen Namen für die Richtlinie für den Zugriff durch externe Benutzer ein.

5.  Geben Sie eine Beschreibung der Richtlinie ein.

6.  Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.

7.  Wählen Sie **Kommunikation mit XMPP-Partnerbenutzern aktivieren** aus.

8.  Klicken Sie auf **Commit ausführen** , um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern.

