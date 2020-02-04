---
title: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für beständigen Chat'
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
ms.openlocfilehash: 49fb5f329851436e503a9e3e42e144353b70017f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Konfigurieren der globalen Richtlinie für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Sie können die standardmäßige globale Richtlinie selbst verwenden, um beständige Chat Einstellungen für alle Benutzer in Ihrer Bereitstellung zu aktivieren. Sie können auch zusätzliche Richtlinien für Websites und Benutzer angeben, um zu steuern, ob der beständige Chat für bestimmte Benutzer und Websites aktiviert oder deaktiviert ist.

Sie können die globale Richtlinie nicht löschen. Wenn Sie versuchen, Sie zu löschen, wird die Konfiguration auf die Standardwerte zurückgesetzt.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren von Einstellungen für den beständigen Chat Server finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Konfigurieren von beständigen Chat Serveroptionen Global oder für den Serverpool für beständigen Chat in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>So konfigurieren Sie die globale Richtlinie für beständigen Chat

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der lync Server-Systemsteuerung auf **beständigen Chat**und dann auf **Richtlinie für beständigen Chat**.

4.  Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:
    
      - Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.
    
      - Geben Sie in **Beschreibung**Details zu den Richtlinien für Benutzer an (beispielsweise globale Richtlinie für centralSiteName).
    
      - Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht explizit über eine Website Richtlinie oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .

6.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

