---
title: 'Lync Server 2013: Erstellen einer Standortrichtlinie für beständigen Chat'
TOCTitle: Erstellen einer Standortrichtlinie für beständigen Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204693(v=OCS.15)
ms:contentKeyID: 49293246
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer Standortrichtlinie für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Für jeden bereitgestellten Standort können Sie eine standortspezifische Richtlinie für den Beständiger Chat erstellen.

Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.


> [!NOTE]
> Wenn Sie den Server für beständigen Chat konfigurieren und verwenden möchten, müssen Sie zunächst mit dem Topologie-Generator die Server für beständigen Chat-Unterstützung der Topologie hinzufügen und die Topologie anschließend veröffentlichen. Einzelheiten dazu finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren der Konfigurationseinstellungen für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Konfigurieren von Optionen für den Server für beständigen Chat auf globaler oder Poolebene in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## So erstellen Sie für einen Standort eine Richtlinie für Beständiger Chat

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im Menü **Start** die Lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Lync Server-Systemsteuerung anwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat**, und klicken sei dann auf **Beständiger Chat-Richtlinie** .
    

    > [!IMPORTANT]
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</A>.



4.  Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie** .

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.

6.  Gehen Sie unter **Neu Beständiger Chat Richtlinie** folgendermaßen vor:
    
      - Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. "Redmond").
    
      - Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)
    
      - Um den Beständiger Chat für alle Standorte zu kontrollieren, die nicht spezifisch durch eine Standortrichtlinie abgedeckt werden, aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Aktivieren Beständiger Chat**.

7.  Klicken Sie auf **Commit** .

