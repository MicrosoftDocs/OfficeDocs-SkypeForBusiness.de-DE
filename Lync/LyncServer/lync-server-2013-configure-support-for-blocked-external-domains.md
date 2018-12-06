---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für blockierte externe Domänen'
TOCTitle: Konfigurieren der Unterstützung für blockierte externe Domänen
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49293899
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Unterstützung für blockierte externe Domänen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche Domänen (k)einen Verbund mit Ihrer Organisation eingehen können. Die Liste der blockierten Domänen fungiert als Sperrliste (mit einer expliziten Auflistung der Einträge, die nicht zulässig sind). Sie findet bei der Erkennung von Verbunddomänen Anwendung, sofern die entsprechende Option aktiviert wurde. Nähere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Blockieren Sie eine oder mehrere externe Domänen vom Herstellen einer Verbindung mit Ihrer Organisation. Fügen Sie hierzu die Domäne der Liste blockierter Domänen hinzu.

## So fügen Sie der Liste blockierter Domänen eine externe Domäne hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** .

4.  Klicken Sie auf **Partnerdomänen** , auf **Neu** und dann auf **Blockierte Domäne** .

5.  Führen Sie unter **Neue Partnerdomänen** die folgende Aktion aus:
    
      - Geben Sie im Feld **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein, die blockiert werden soll.
        

        > [!NOTE]
        > Der Name darf maximal 256 Zeichen umfassen.<BR>Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG> eingeben, wird als Suchergebnis auch die Domäne <STRONG>it.contoso.com</STRONG> zurückgegeben.<BR>Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden. Lync Server 2013 verhindert dies automatisch, sodass Sie Ihre Listen nicht synchronisieren müssen.

    
      - Im Feld **Kommentar** können Sie Informationen zur Konfiguration eingeben, die Sie mit anderen Systemadministratoren teilen möchten. Dieses Feld ist optional.

6.  Klicken Sie auf **Commit** .

7.  Wiederholen Sie die Schritte 4 bis 6 für jeden Verbundpartner, den Sie blockieren möchten.

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren. Nähere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Nähere Informationen finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

