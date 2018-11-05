---
title: 'Lync Server 2013: Erstellen einer Benutzerrichtlinie für beständigen Chat'
TOCTitle: Erstellen einer Benutzerrichtlinie für beständigen Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205170(v=OCS.15)
ms:contentKeyID: 49295038
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer Benutzerrichtlinie für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In der Lync Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern unter **Benutzer** zugewiesen werden können.

Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.


> [!NOTE]
> Wenn Sie den Server für beständigen Chat konfigurieren und verwenden möchten, müssen Sie zunächst mit dem Topologie-Generator die Server für beständigen Chat-Unterstützung der Topologie hinzufügen und die Topologie anschließend veröffentlichen. Einzelheiten dazu finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren der Konfigurationseinstellungen für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## So erstellen Sie eine Benutzerrichtlinie für Beständiger Chat

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im Menü **Start** die Lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Lync Server-Systemsteuerung anwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    

    > [!IMPORTANT]
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Siehe <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.



3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat**, und klicken sei dann auf **Beständiger Chat-Richtlinie** .

4.  Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie** .

5.  Führen Sie unter **Neue Richtlinie für Beständiger Chat** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.
    
      - Geben Sie unter **Beschreibung** Einzelheiten über den Zweck der Benutzerrichtlinie an (beispielsweise Richtlinie für Chats vom Typ Beständiger Chat für einen bestimmten Benutzer).
    
      - Wenn Sie Chats vom Typ Beständiger Chat für alle Benutzer festlegen möchten, die nicht über eine Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Beständiger Chat aktivieren**.

6.  Klicken Sie auf **Commit** .

