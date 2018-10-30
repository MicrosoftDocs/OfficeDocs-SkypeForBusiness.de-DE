---
title: 'Lync Server 2013: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer'
TOCTitle: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521007(v=OCS.15)
ms:contentKeyID: 49294237
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Standardmäßig werden alle Benutzer daran gehindert, anonyme Benutzer zur Teilnahme an einer Besprechung einzuladen. Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine Konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese Konferenzrichtlinie auf bestimmte Benutzer anwenden. Ausführliche Informationen zur Konfiguration von Konferenzrichtlinien für die Unterstützung anonymer Benutzer finden Sie unter [Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) und [Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Verwenden Sie das Verfahren in diesem Abschnitt, um eine bereits erstellte Konferenzrichtlinie auf einen oder mehrere Benutzer oder Benutzergruppen anzuwenden.


> [!NOTE]
> Neben der Konfiguration und Anwendung einer Richtlinie müssen Sie außerdem die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren, um Benutzern das Einladen anonymer Benutzer zu ermöglichen. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013</A>.



## So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und führen Sie einen der folgenden Schritte aus:
    
    1.  Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie** . Erstellen Sie einen eindeutigen Namen im Feld **Name** , der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableAnonymous** für eine Benutzerrichtlinie, welche die Kommunikation mit anonymen Benutzern aktiviert).
    
    2.  Klicken Sie zum Konfigurieren einer vorhandenen Benutzerrichtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen** .

4.  Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen **Teilnehmern das Einladen anonymer Benutzer gestatten** .

5.  Klicken Sie auf **Commit** .

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

7.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen** .

8.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Konferenzrichtlinie** die Benutzerrichtlinie mit der Konfiguration für den anonymen Benutzerzugriff aus, die Sie auf diesen Benutzer anwenden möchten.
    

    > [!NOTE]
    > Die Einstellungen <STRONG>&lt;Automatisch&gt;</STRONG> wenden die Einstellungen der Standardserverinstallation an und werden vom Server automatisch zugewiesen.



Damit Benutzer anonyme Benutzer zu Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren. Ausführliche Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in der Bereitstellungsdokumentation oder der Betriebsdokumentation.

