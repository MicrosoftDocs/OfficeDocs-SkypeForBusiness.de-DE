---
title: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für den beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4131bca64c8faab6f1b616a02994fbccd9b435dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Konfigurieren der globalen Richtlinie für den beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Sie können die standardmäßige globale Richtlinie allein verwenden, um Einstellungen für beständigen Chat für alle Benutzer in Ihrer Bereitstellung zu aktivieren. Sie können auch zusätzliche Richtlinien für Websites und Benutzer festlegen, um zu steuern, ob persistenter Chat für bestimmte Benutzer und Websites aktiviert oder deaktiviert ist.

Die globale Richtlinie kann nicht gelöscht werden. Beim Versuch, die globale Richtlinie zu löschen, wird die Konfiguration auf die Standardwerte zurückgesetzt.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um die Unterstützung für beständigen Chat Server zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigen Chat Servern zur Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren von Konfigurationseinstellungen für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configure persistent Chat Server Options Globally or for persistent Chat Serverpool in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>So konfigurieren Sie die globale Richtlinie für den beständigen Chat

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in lync Server-Systemsteuerung auf **beständiger Chat**und dann auf **Richtlinie für beständigen Chat**.

4.  Klicken Sie in der Liste der Richtlinien auf **Global**, und klicken Sie dann auf **Bearbeiten** und **Details anzeigen**.

5.  Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:
    
      - Geben Sie in **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen "Global" nicht verwenden möchten.
    
      - Geben Sie in **Beschreibung**Details zu den Anforderungen der Benutzerrichtlinie an (beispielsweise globale Richtlinie für centralSiteName).
    
      - Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht speziell über eine Standort-oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .

6.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

