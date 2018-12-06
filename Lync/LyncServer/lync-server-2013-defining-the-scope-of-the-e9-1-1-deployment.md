---
title: 'Lync Server 2013: Definieren des Umfangs der E9-1-1-Bereitstellung'
TOCTitle: Definieren des Umfangs der E9-1-1-Bereitstellung
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425775(v=OCS.15)
ms:contentKeyID: 49293525
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren des Umfangs der E9-1-1-Bereitstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Bevor Sie Microsoft Lync Server 2013 für Notfalldienste (E9-1-1) konfigurieren, müssen Sie Ihre E9-1-1-Bereitstellung planen. Stellen Sie sich die folgenden Fragen:

  - **Worin bestehen die Richtlinien und Vorschriften in Ihrer Organisation im Hinblick auf E9-1-1?**  
    Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als "Telefonsysteme mit mehreren Leitungen" oder "Mehrleitungstelefonsystemen" bezeichnet) unterscheiden sich von Staat zu Staat. Holen Sie von Ihrem Team aus der Rechtsabteilung Informationen zu den Vorschriften ein, die für Ihre Bereitstellung von Lync Server in den jeweiligen Regionen einzuhalten sind.

<!-- end list -->

  - **Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**  
    Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten, und Standorte außerhalb der USA können ausgeschlossen werden.

<!-- end list -->

  - **Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**  
    Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen. Wenn es bei Verwendung zentralisierter E9-1-1-SIP-Trunks zu einem WAN-Ausfall kommt, können angemeldete Clients möglicherweise keinen Standort von Standortinformationsdienst abrufen oder keine Verbindung mit dem Anbieter für die Notrufunterstützung herstellen. Lync Server bietet verschiedene Strategien für das Gewährleisten von VoIP-Ausfallsicherheit in Zweigstellen, darunter: Konfigurieren ausfallsicherer Datennetzwerke, Bereitstellen eines SIP-Trunks an jedem Zweigstellenstandort oder Weiterleiten von Notrufen an das lokale Gateway bei einem Ausfall. Ausführliche Informationen finden Sie unter [Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**  
    Eine automatische Standorterkennung ist nur für Clients verfügbar, die sich innerhalb des Netzwerks der Organisation befinden. Ihre Organisation muss daher entscheiden, ob E9-1-1-Anrufe von Lync-Clients, die sich nicht vor Ort befinden, unterstützt werden sollen. Möchten Sie es Benutzern beispielsweise ermöglichen, Notrufe zu tätigen, wenn sie von zu Hause aus oder bei einem Kunden arbeiten? Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client den Benutzer zur Angabe eines Standorts auffordern. Da diese von den Benutzern angegebenen Standorte jedoch nicht vorab mit der MSAG (Master Street Address Guide)-Datenbank abgeglichen werden können, muss eine verantwortliche Person beim Anbieter für die Notrufunterstützung die Gültigkeit des Standorts in einem Gespräch mit dem Anrufer überprüfen, bevor der Anruf an die Rettungsleitstelle weitergeleitet wird.
    

    > [!NOTE]
    > Lync-Clients von Benutzern, die über VPNs eine Verbindung mit dem Netzwerk Ihrer Organisation herstellen, können interne IP-Adressinformationen abrufen. Da diese Adressen jedoch nicht zum Identifizieren des tatsächlichen Standorts des Benutzers verwendet werden können, ist es sehr wichtig, dass VPN-Subnetze aus dem Standortinformationsdienst ausgeschlossen werden.



<!-- end list -->

  - **Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**  
    Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter für die Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten VoIP-Richtlinien zu, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird.

