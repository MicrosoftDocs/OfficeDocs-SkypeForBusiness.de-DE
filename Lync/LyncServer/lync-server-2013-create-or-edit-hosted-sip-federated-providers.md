---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern'
TOCTitle: Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ552445(v=OCS.15)
ms:contentKeyID: 49293173
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Über Verbindungen mit Instant Messaging-Diensten von gehosteten Anbietern können Benutzer in Ihrer Organisation per Sofortnachricht mit Benutzern von Instant Messaging-Diensten kommunizieren, die von gehosteten Anbietern bereitgestellt werden, darunter Microsoft Office 365 und Lync Online.

Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers des Anbieters sowie der Standardüberprüfungsstufe **Benutzern nur die Kommunikation mit den Personen in ihren Kontaktlisten erlauben, die diesen Anbieter verwenden** konfiguriert.

Verwenden Sie zum Erstellen oder Bearbeiten von gehosteten Anbietern das folgende Verfahren:

## So erstellen oder bearbeiten Sie gehostete Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partneranbieter** .

4.  Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **Neu** und anschließend auf **Gehosteter Anbieter** .

5.  Wenn Sie in der Liste der gehosteten Anbieter einen Eintrag bearbeiten müssen, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen** .

6.  Auf der Seite **SIP-Partneranbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder ändern:
    
      - **Kommunikation mit diesem Anbieter aktivieren**    Die Auswahl dieser Einstellung ermöglicht die Kommunikation mit den Benutzen dieses Anbieters.
    
      - **Anbietername:**    Erforderliche Eigenschaft. Geben Sie den Namen des Anbieters ein, wie er in der Auflistung der SIP-Partneranbieter angezeigt wird.
    
      - **Zugriffs-Edgedienst (FQDN):**    Erforderliche Eigenschaft; geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgedienstes des gehosteten Anbieters ein, den Sie konfigurieren. Diese Informationen sollten vom gehosteten Anbieter bereitgestellt und nur dann geändert werden, wenn der gehostete Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts beim gehosteten Anbieter vornimmt.
    
      - **Standardüberprüfungsstufe:**    Mit der Standardeinstellung **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** wird die Kommunikation auf Kontakte beschränkt, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Die Auswahl der Option **Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet** entfernt die Einschränkung, dass Sie eine Kontaktanfrage erhalten und angenommen haben müssen. Diese Einstellung hat keine Auswirkungen darauf, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken Sie auf **Commit** , um die Änderungen zu speichern, oder auf **Abbrechen** , um die Änderungen zu verwerfen.

## Siehe auch

#### Aufgaben

[Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

