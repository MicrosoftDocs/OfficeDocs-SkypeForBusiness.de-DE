---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für zulässige externe Domänen'
TOCTitle: Konfigurieren der Unterstützung für zulässige externe Domänen
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425908(v=OCS.15)
ms:contentKeyID: 49293779
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche spezifischen Domänen einen Partnerverbund mit Ihrer Organisation eingehen können. Konfigurieren Sie eine oder mehrere spezifische externe Domänen als zulässige Partnerdomänen. Fügen Sie hierzu jede Domäne der Liste zulässiger Domänen hinzu. Selbst wenn die Suche von Verbundpartnern für Ihre Organisation aktiviert ist, führen Sie diesen Schritt aus, wenn es sich bei der Domäne um einen Verbundpartner handelt, der mit mehr als 1.000 Ihrer Benutzer kommunizieren oder mehr als 20 Nachrichten pro Sekunde senden muss. Ist die Suche von Verbundpartnern für Ihre Organisation nicht aktiviert, können nur Benutzer aus externen Domänen am Instant Messaging und an Konferenzen mit Benutzern Ihrer Organisation teilnehmen, die Sie der Liste zulässiger Domänen hinzugefügt haben. Wenn Sie den Zugriff einer Partnerdomäne auf einen bestimmten Server beschränken möchten, auf dem der Zugriffs-Edgedienst des Verbundpartners ausgeführt wird, können Sie für jede Domäne in der Liste zulässiger Domänen den Domänennamen des Servers angeben, auf dem der Zugriffs-Edgedienst ausgeführt wird.


> [!NOTE]
> Dieses Verfahren beschreibt, wie Sie die Unterstützung für bestimmte Domänen konfigurieren. Zur Implementierung der Unterstützung für Partnerbenutzer gehört jedoch auch, dass Sie die Unterstützung für Partnerbenutzer für Ihre Organisation aktivieren sowie Richtlinien konfigurieren und anwenden, um zu steuern, welche Benutzer mit Partnerbenutzern zusammenarbeiten können. Ausführliche Informationen zum Aktivieren der Unterstützung für Partnerbenutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</A>. Ausführliche Informationen zum Konfigurieren von Richtlinien zur Steuerung des Partnerverbunds finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</A>.



## So fügen Sie eine externe Domäne der Liste zulässiger Domänen hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Partnerdomänen** .

4.  Klicken Sie auf der Seite **Partnerdomänen** auf **Neu** und anschließend auf **Zulässige Domäne** .

5.  Führen Sie unter **Neue Partnerdomänen** die folgende Aktion aus:
    
      - Geben Sie unter **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein.
        

        > [!NOTE]
        > Dieser Name muss eindeutig sein und darf noch nicht als zulässige Domäne für diesen Server vorliegen, auf dem der Zugriffs-Edgedienst ausgeführt wird. Der Name darf höchstens 256&nbsp;Zeichen lang sein.<BR>Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG> eingeben, wird als Suchergebnis auch die Domäne <STRONG>it.contoso.com</STRONG> zurückgegeben.<BR>Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden. Lync Server 2013 verhindert dies automatisch, sodass Sie Ihre Listen nicht synchronisieren müssen.

    
      - Wenn Sie den Zugriff für diese Partnerdomäne auf Benutzer eines bestimmten Servers beschränken möchten, auf dem der Zugriffs-Edgedienst ausgeführt wird, geben Sie unter **Zugriffs-Edgedienst (FQDN)** den FQDN des Servers der Partnerdomäne ein, auf dem der Zugriffs-Edgedienst ausgeführt wird.
    
      - Wenn Sie zusätzliche Informationen bereitstellen möchten, geben Sie unter **Kommentar** Informationen ein, die Sie anderen Systemadministratoren über diese Konfiguration mitteilen möchten.

6.  Klicken Sie auf **Commit** .

7.  Wiederholen Sie die Schritte 4 bis 6 für jede Verbundpartnerdomäne, die Sie zulassen möchten.

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren. Nähere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Nähere Informationen finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

