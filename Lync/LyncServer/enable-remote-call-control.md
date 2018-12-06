---
title: Aktivieren der Remoteanrufsteuerung
TOCTitle: Aktivieren der Remoteanrufsteuerung
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204664(v=OCS.15)
ms:contentKeyID: 49293139
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Remoteanrufsteuerung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Mit der Remoteanrufsteuerung können Benutzer ihre Festnetztelefone mithilfe von Lync Server 2013 steuern. Wenn Sie die Remoteanrufsteuerung in Ihrer Vorversionsumgebung bereitgestellt haben und zu Lync Server 2013 migrieren möchten, müssen Sie die folgenden Schritte ausführen:

1.  Installieren Sie ein SIP/CSTA-Gateway, und konfigurieren Sie es für die Kommunikation mit dem Festnetztelefon. Sie müssen diesen Schritt bei der Bereitstellung Ihres Lync Server 2013-Pilotpools ausführen.

2.  Nach dem Zusammenführen der Topologie und der Migration der Richtlinien und Einstellungen konfigurieren Sie Lync Server 2013 so, dass CSTA-Anforderungen an das SIP/CSTA-Gateway weitergeleitet werden. Es handelt sich hierbei um einen manuellen Schritt nach der automatischen Migration. Führen Sie zur Konfiguration des Routings für CSTA-Anforderungen Folgendes aus:
    
      - Entfernen Sie Einträge der Vorversion für autorisierte Hosts (in Lync Server 2013 als *vertrauenswürdige Servereinträge* bezeichnet). Wenn Sie Benutzer aus Ihrer Vorversionsbereitstellung migrieren, achten Sie darauf, alle vorhandenen Einträge für autorisierte Hosts zu entfernen, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie neue Einträge für vertrauenswürdige Anwendungen im Lync Server 2013-Pilotpool konfigurieren. Ausführliche Informationen über das Entfernen von Einträgen der Vorversion für autorisierte Hosts finden Sie unter [Entfernen eines Eintrags für autorisierte Hosts](remove-an-authorized-host-entry.md).
    
      - Konfigurieren Sie eine statische Route für die Remoteanrufsteuerung. Sie können eine statische Route für einzelne Pools konfigurieren, die die Remoteanrufsteuerung unterstützen sollen. Alternativ können Sie eine globale statische Route konfigurieren, damit jeder Pool, der nicht mit einer statischen Route auf Poolebene konfiguriert wurde, die globale statische Route verwendet. Ausführliche Informationen über die Konfiguration der statischen Route finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in der Bereitstellungsdokumentation.
    
      - Konfigurieren Sie einen Eintrag einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in jedem Pool, der die Remoteanrufsteuerung unterstützen soll. Ausführliche Informationen über die Konfiguration eines Eintrags für vertrauenswürdige Anwendungen finden Sie unter [Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in der Bereitstellungsdokumentation.

3.  Wenn Sie ein SIP/CSTA-Gateway bereitgestellt haben, das TCP (Transmission Control Protocol) zur Verbindung mit Lync Server 2013 verwendet, definieren Sie die IP-Adresse des Gateways im Topologie-Generator. Ausführliche Informationen über die Definition der IP-Adresse finden Sie unter [Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in der Bereitstellungsdokumentation.

4.  Konfigurieren Sie Lync 2013-Benutzer für die Remoteanrufsteuerung, indem Sie die Remoteanrufsteuerung aktivieren und einen Leitungsserver-URI (Uniform Resource Identifier) sowie einen Anschluss-URI zuweisen. Wenn Sie Benutzer aus der Vorversionsbereitstellung zu Lync Server 2013 migrieren, werden die Einstellungen der Remoteanrufsteuerung zusammen mit den anderen Benutzereinstellungen migriert.

5.  Wenn Sie die Normalisierungsregeln für Rufnummern im Adressbuch in Ihrer Vorversionsbereitstellung angepasst haben, müssen Sie nach der automatischen Migration der Richtlinien und Einstellungen einige manuelle Aufgaben durchführen, um die angepassten Normalisierungsregeln zu migrieren. Wenn Sie die Normalisierungsregeln nicht angepasst haben, wird das Adressbuch mit der restlichen Topologie migriert. Ausführliche Informationen über die manuelle Migration benutzerdefinierter Normalisierungsregeln finden Sie unter [Migrieren eines Adressbuchs](migrate-address-book_1.md).

