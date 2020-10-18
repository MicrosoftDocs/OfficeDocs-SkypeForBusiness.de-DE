---
title: 'Lync Server 2013: Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe'
description: 'Lync Server 2013: Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 168fa795303bbcf3f3eef4bfc817aa98d763d1ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573481"
---
# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Wenn ein Benutzer für lync Server 2013 aktiviert wurde, können Sie entsprechende Richtlinien auf bestimmte Benutzer anwenden, um Sie für den Server für beständigen Chat zu aktivieren oder zu deaktivieren.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um die Unterstützung für beständigen Chat Server zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigen Chat Servern zur Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Informationen zum Konfigurieren von Konfigurationseinstellungen für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configure persistent Chat Server Options Globally or for persistent Chat Serverpool in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Benutzerrichtlinie für beständigen Chat auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>So wenden Sie eine Benutzerrichtlinie für beständigen Chat auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie im Abschnitt **lync Server Benutzer bearbeiten** unter **Richtlinie für beständigen Chat**die Benutzerrichtlinie für beständigen Chat aus, die Sie anwenden möchten.
    
    <div>
    

    > [!NOTE]  
    > Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen wird die standardmäßige effektive Richtlinie angewendet. Diese Einstellungen werden automatisch vom Server angewendet.

    
    </div>

6.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

