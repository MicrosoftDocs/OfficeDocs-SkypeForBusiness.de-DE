---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern'
TOCTitle: Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398349(v=OCS.15)
ms:contentKeyID: 49294015
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Über Verbindungen mit öffentlichen Instant Messaging-Diensten können Benutzer in Ihrer Organisation per Sofortnachricht mit Benutzern von Sofortnachrichtendiensten kommunizieren, die von öffentlichen Sofortnachrichten-Dienstanbietern bereitgestellt werden, z. B. von Windows Live Messenger, von Yahoo\! und von AOL.

Die Lync Server 2013 beinhaltet Konfigurationen für die öffentlichen Sofortnachrichtendienste von Windows Live, Yahoo\! und AOL. Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers für den jeweiligen Anbieter sowie mit der Standardüberprüfungsstufe **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** konfiguriert.

In der Standardeinstellung ist kein öffentlicher Anbieter aktiviert. Bevor Sie die öffentlichen Anbieter aktivieren, sollten Sie zunächst die Lizenzvereinbarung und die Bereitstellungsmaßnahmen abschließen. Es ist möglich, die Anbieter vor Abschluss der Lizenzvereinbarung und der Bereitstellungsmaßnahmen zu aktivieren. Benutzer können jedoch nicht mit Kontakten dieser Anbieter kommunizieren, bevor die Vorbereitungsmaßnahmen nicht abgeschlossen sind. Nähere Informationen zur Lizenzierung sowie zur Bereitstellung öffentlicher Anbieter finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Mit den folgenden Verfahren können Sie öffentliche Anbieter erstellen oder bearbeiten:

## So erstellen oder bearbeiten Sie öffentliche Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partneranbieter** .

4.  Wenn Sie einen öffentlichen Anbieter erstellen möchten, klicken Sie auf **Neu** und dann auf **Öffentlicher Anbieter** .

5.  Um einen Eintrag aus der Liste der öffentlichen Anbieter zu bearbeiten, wählen Sie einen öffentlichen Anbieter aus, klicken auf **Bearbeiten** und dann auf **Details anzeigen** .

6.  Auf der Seite **SIP-Partneranbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder ändern:
    
      - **Kommunikation mit diesem Anbieter aktivieren**    Wenn Sie diese Einstellung auswählen, wird die Sofortnachrichtenfunktion für Benutzer dieses Anbieters aktiviert.
    
      - **Anbietername:**    Erforderliche Eigenschaft. Geben Sie den Namen des Anbieters ein, wie er in der Auflistung der SIP-Partneranbieter angezeigt wird.
    
      - **Zugriffs-Edgedienst (FQDN):**    Erforderliche Eigenschaft. Geben Sie den vollqualifizierten Domänennamen für den Zugriffs-Edgedienst des Anbieters ein, den Sie konfigurieren möchten. Diese Informationen werden standardmäßig bereitgestellt. Sie sollten nur geändert werden, wenn beim öffentlichen Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts vorgenommen wird.
    
      - **Standardüberprüfungsstufe:**    Mit der Standardeinstellung **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** wird die Kommunikation auf Kontakte beschränkt, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Durch Auswählen von **Benutzer können mit allen Benutzern mit diesem Anbieter kommunizieren** wird die Einschränkung entfernt, dass eine Kontakteinladung empfangen und angenommen worden sein muss. Diese Einschränkung hat keine Auswirkungen darauf, welche Benutzer aus dem Netzwerk des öffentlichen Anbieters mit Ihnen Kontakt aufnehmen können.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken Sie auf **Commit** , um die Änderungen zu speichern, oder auf **Abbrechen** , um die Änderungen zu verwerfen.

## Siehe auch

#### Aufgaben

[Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

