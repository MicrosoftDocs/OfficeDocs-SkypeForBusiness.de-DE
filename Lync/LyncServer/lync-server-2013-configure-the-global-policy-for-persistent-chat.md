---
title: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für beständigen Chat'
TOCTitle: Konfigurieren der globalen Richtlinie für beständigen Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204951(v=OCS.15)
ms:contentKeyID: 49294177
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der globalen Richtlinie für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Sie können die globale Standardrichtlinie verwenden, um Einstellungen der Funktion Beständiger Chat für alle Benutzer in Ihrer Bereitstellung zu aktivieren. Sie können auch zusätzliche Richtlinien für Standorte und Benutzer angeben, um die Funktion Beständiger Chat für bestimmte Benutzer und Standorte zu aktivieren oder zu deaktivieren.

Die globale Richtlinie kann nicht gelöscht werden. Wenn Sie versuchen, die globale Richtlinie zu löschen, wird die Konfiguration auf die Standardwerte zurückgesetzt.


> [!NOTE]
> Wenn Sie den Server für beständigen Chat konfigurieren und verwenden möchten, müssen Sie zunächst mit dem Topologie-Generator die Server für beständigen Chat-Unterstützung der Topologie hinzufügen und die Topologie anschließend veröffentlichen. Einzelheiten dazu finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren der Konfigurationseinstellungen für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## So konfigurieren Sie die globale Richtlinie für Beständiger Chat

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im Startmenü den Eintrag Lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die die Admin-URL ein. Einzelheiten über die verschiedenen Methoden, mit denen Sie die Lync Server-Systemsteuerung starten können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation.
    

    > [!IMPORTANT]
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Einzelheiten dazu finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.



3.  Klicken Sie in der Lync Server-Systemsteuerung auf **Beständiger Chat**, und klicken Sie dann auf **Beständiger Chat Richtlinie** .

4.  Klicken Sie in der Liste der Richtlinien auf **Global** , dann auf **Bearbeiten** und anschließend auf **Details anzeigen** .

5.  Führen Sie in **Beständiger Chat-Richtlinie bearbeiten - Global** Folgendes durch:
    
      - Geben Sie in **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert "Global" nicht verwenden möchten.
    
      - Geben Sie in **Beschreibung** Einzelheiten dazu an, was für eine Richtlinie das ist (z. B. globale Richtlinie für *centralSiteName* ).
    
      - Zur Steuerung des Features Beständiger Chat für alle Standorte und Benutzer, die nicht explizit über eine bestimmte Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Aktivieren Beständiger Chat**.

6.  Klicken Sie auf **Commit** .

