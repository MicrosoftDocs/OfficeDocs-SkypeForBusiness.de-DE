---
title: 'Lync Server 2013: Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe'
TOCTitle: Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205038(v=OCS.15)
ms:contentKeyID: 49294567
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Benutzern, die für Lync Server 2013 aktiviert wurden, können Sie entsprechende Richtlinien zuweisen, um sie für den Server für beständigen Chat zu aktivieren oder zu deaktivieren.


> [!NOTE]
> Wenn Sie den Server für beständigen Chat konfigurieren und verwenden möchten, müssen Sie zunächst mit dem Topologie-Generator die Server für beständigen Chat-Unterstützung der Topologie hinzufügen und die Topologie anschließend veröffentlichen. Einzelheiten dazu finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren der Konfigurationseinstellungen für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene in Lync Server 2013</A> in der Bereitstellungsdokumentation.



Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Benutzerrichtlinie für den Beständiger Chat auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.

## So wenden Sie eine Benutzerrichtlinie für den Beständiger Chat auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im Menü **Start** die Lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Lync Server-Systemsteuerung anwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen** .

5.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Beständiger Chat-Richtlinie** die Beständiger Chat-Benutzerrichtlinie aus, die Sie zuweisen möchten.
    

    > [!NOTE]
    > Die Einstellung <STRONG>&lt;Automatisch&gt;</STRONG> wendet die standardmäßig effektive Richtlinie an. Diese Einstellungen werden automatisch vom Server angewendet.



6.  Klicken Sie auf **Commit** .

