---
title: 'Lync Server 2013: Konfigurieren von Add-Ins für Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb6525f67f22e09c4bf7ea40f575b3981e9a55c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Konfigurieren von Add-Ins für Chatrooms in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In der lync Server 2013-Systemsteuerung können Sie mithilfe des **Add-in-** Abschnitts der Seite "beständiger **Chat** " URLs mit beständigen Chatrooms verknüpfen. Diese URLs werden im lync 2013-Client im Chatroom im Bereich Konversations Erweiterbarkeit angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins Add-Ins hinzufügen, und Chatroom-Manager/-Entwickler müssen Räume mit einem der registrierten Add-ins verknüpfen, bevor Benutzer dieses Upgrade in Ihrem lync 2013-Client sehen können.

Add-Ins werden verwendet, um die in-Room-Erfahrung zu erweitern. Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung zeigt, die abfängt, wenn ein Börsenticker in einem Chatroom bereitgestellt wird, und den Aktienverlauf im Bereich "Erweiterbarkeit" anzeigt. Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-in, um einen freigegebenen Kontext einzubeziehen, beispielsweise "Top of mindi" oder "Tagesthema".

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>So konfigurieren Sie Add-ins für Chatrooms

1.  Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter Konfigurieren des beständigen <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Chat Servers mithilfe von Windows PowerShell</A> -Cmdlets in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.
    
    Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.

4.  Klicken Sie auf der Seite **Add-In** auf **Neu**.

5.  Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.

6.  Gehen Sie unter **Neues Add-In** wie folgt vor:
    
      - Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.
    
      - Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Öffnen der lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)  


[Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

