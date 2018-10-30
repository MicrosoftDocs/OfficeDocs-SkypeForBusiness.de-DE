---
title: Bereitstellen eines Pilot-Edgeservers
TOCTitle: Bereitstellen eines Pilot-Edgeservers
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205306(v=OCS.15)
ms:contentKeyID: 49295600
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen eines Pilot-Edgeservers

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Dieses Thema behandelt wichtige Überlegungen, die Sie beachten sollten, bevor Sie Ihren Lync Server 2013- Edgeserver bereitstellen. Die Bereitstellungs- und Konfigurationsprozesse für Lync Server 2013 unterscheiden sich nicht wesentlich von Lync Server 2010. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Schritte finden Sie unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, die eine Beschreibung des Bereitstellungsprozesses sowie Konfigurationsinformationen für den externen Benutzerzugriff enthält.

Überprüfen Sie beim Navigieren durch den Assistenten zum Definieren eines neuen Edgepools die in den folgenden Schritten dargestellten wichtigen Konfigurationseinstellungen. Beachten Sie, dass nur einige der Seiten des Assistenten zum Definieren eines neuen Edgepools abgebildet sind.

**Definieren eines Edgepools**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Navigieren Sie zum Knoten Lync Server 2013. Klicken Sie mit der rechten Maustaste auf **Edgepools** , und klicken Sie dann auf **Neuer Edgepool** .
    
    ![Neuen Edgepool definieren (Dialogfeld)](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Neuen Edgepool definieren (Dialogfeld)")

3.  Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer** .
    
    ![FQDN des Edgepools definieren (Dialogfeld)](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "FQDN des Edgepools definieren (Dialogfeld)")

4.  Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Partnerverbund oder den XMPP-Partnerverbund. Der Partnerverbund und der XMPP-Partnerverbund werden derzeit beide über den Lync Server 2010- Edgeserver der Vorversion geleitet. Diese Features werden in einer späteren Phase der Migration konfiguriert.
    
    ![Funktionen auswählen (Dialogfeld)](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Funktionen auswählen (Dialogfeld)")

5.  Bearbeiten Sie anschließend die folgenden Seiten des Assistenten: **Externe FQDNs** , **Interne IP-Adresse definieren** und **Externe IP-Adresse definieren** .

6.  Wählen Sie auf der Seite **Nächsten Hop definieren** den Director für den nächsten Hop des Lync Server 2010- Edgepool.
    
    ![Nächsten Hop definieren (Dialogfeld)](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Nächsten Hop definieren (Dialogfeld)")

7.  Weisen Sie auf der Seite **Front-End- oder Vermittlungspools zuordnen** zu diesem Zeitpunkt dem Edgepool keinen Pool zu. Der externe Mediendatenverkehr wird derzeit über den Lync Server 2010- Edgeserver der Vorversion geleitet. Diese Einstellung wird in einer späteren Phase der Migration konfiguriert.
    
    ![Front-End-Pools zuordnen (Dialogfeld)](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Front-End-Pools zuordnen (Dialogfeld)")

8.  Klicken Sie auf **Fertig stellen** , und **veröffentlichen** Sie anschließend die Topologie.

9.  Führen Sie die Schritte unter [Installieren von Edgeservern für Lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.

Sie müssen sich unbedingt an die Anweisungen unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation halten. Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar.

Sie sollten jetzt parallel zum Lync Server 2010-Edgeserver der Vorversion eine Bereitstellung des Lync Server 2013-Edgeservers installiert haben. Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren.

