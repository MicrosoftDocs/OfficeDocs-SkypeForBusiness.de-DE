---
title: Bereitstellen eines Pilot-Edgeservers
TOCTitle: Bereitstellen eines Pilot-Edgeservers
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204682(v=OCS.15)
ms:contentKeyID: 49293223
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen eines Pilot-Edgeservers

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

In diesem Thema werden Konfigurationseinstellungen hervorgehoben, mit denen Sie vor der Bereitstellung des Lync Server 2013- Edgeservers vertraut sein sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotedgepools hervorgehoben. Ausführliche Schritte finden Sie unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, die eine Beschreibung des Bereitstellungsprozesses sowie Konfigurationsinformationen für den externen Benutzerzugriff enthält.

Überprüfen Sie beim Navigieren durch den Assistenten zum Definieren eines neuen Edgepools die in den folgenden Schritten dargestellten wichtigen Konfigurationseinstellungen. Beachten Sie, dass nur einige der Seiten des Assistenten zum Definieren eines neuen Edgepools abgebildet sind.

**Definieren eines Edgepools**

1.  Öffnen Sie mithilfe des Topologie-Generators die Pilotpooltopologie.

2.  Navigieren Sie zum Knoten Lync Server 2013. Klicken Sie mit der rechten Maustaste auf **Edgepools** , und klicken Sie dann auf **Neuer Edgepool** .
    
    ![Neuen Edgepool definieren (Dialogfeld)](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Neuen Edgepool definieren (Dialogfeld)")

3.  Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer** .
    
    ![FQDN des Edgepools definieren (Dialogfeld)](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "FQDN des Edgepools definieren (Dialogfeld)")

4.  Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund. Der Verbund und der XMPP-Partnerverbund werden derzeit über den Office Communications Server 2007 R2- Edgeserver der Vorgängerversion geleitet. Diese Funktionen werden in einer späteren Phase der Migration konfiguriert.
    
    ![Funktionen auswählen (Dialogfeld)](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Funktionen auswählen (Dialogfeld)")

5.  Bearbeiten Sie anschließend die folgenden Seiten des Assistenten: **IP-Optionen auswählen** , **Externe FQDNs** , **Interne IP-Adresse definieren** und **Externe IP-Adresse definieren** .

6.  Wählen Sie auf der Seite **Nächsten Hop definieren** den Director für den nächsten Hop des Lync Server 2013- Edgepool.
    
    ![Neuen Edgepool definierten (Dialogfeld), Nächster Hoppool (Liste)](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Neuen Edgepool definierten (Dialogfeld), Nächster Hoppool (Liste)")

7.  Weisen Sie auf der Seite **Front-End-Pools zuordnen** zu diesem Zeitpunkt dem Edgepool keinen Pool zu. Der externe Mediendatenverkehr wird derzeit über den alten Office Communications Server 2007 R2- Edgeserver geleitet. Diese Einstellung wird in einer späteren Phase der Migration konfiguriert.
    
    ![Neuen Edgepool definieren (Dialogfeld)](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Neuen Edgepool definieren (Dialogfeld)")

8.  Klicken Sie auf **Fertig stellen** , und **veröffentlichen** Sie anschließend die Topologie.

9.  Führen Sie die Schritte unter [Installieren von Edgeservern für Lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.

Sie müssen sich unbedingt an die Anweisungen unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation halten. Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar.

Sie sollten jetzt über eine Office Communications Server 2007 R2-Edgeserverbereitstellung der Vorgängerversion verfügen, die am Vorhandensein von "BackCompatSite" parallel zu einer Lync Server 2013-Edgeserverbereitstellung zu erkennen ist. Der Verbund ist für die Verwendung des Office Communications Server 2007 R2 Director konfiguriert. Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren.

![Topologie-Generator mit OCS-Edgeserver](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topologie-Generator mit OCS-Edgeserver")

