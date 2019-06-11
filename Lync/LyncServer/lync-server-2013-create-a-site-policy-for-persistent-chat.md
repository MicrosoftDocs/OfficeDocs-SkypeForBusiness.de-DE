---
title: 'Lync Server 2013: Erstellen einer Standortrichtlinie für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be98028bf06c20c82dca98fc3bc20d25e97a94c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>Erstellen einer Standortrichtlinie für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Für jede Website, die Sie bereitgestellt haben, können Sie eine Website spezifische Richtlinie für beständigen Chat erstellen.

Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren von Einstellungen für den beständigen Chat Server finden Sie unter Konfigurieren von beständigen <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Chat Serveroptionen Global oder für den Serverpool für beständigen Chat in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>So erstellen Sie eine Richtlinie für beständigen Chat für eine Website

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter Konfigurieren des beständigen <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Chat Servers mithilfe von Windows PowerShell</A> -Cmdlets in der Bereitstellungsdokumentation.

    
    </div>

4.  Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.

6.  Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).
    
      - Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)
    
      - Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

