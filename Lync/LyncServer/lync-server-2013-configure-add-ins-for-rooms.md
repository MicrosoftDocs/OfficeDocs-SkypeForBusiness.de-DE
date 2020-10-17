---
title: 'Lync Server 2013: Konfigurieren von Add-Ins für Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8779e770ca96cbfc34bbbc1f1897df1f5eb9ea03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523052"
---
# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Konfigurieren von Add-Ins für Chatrooms in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

In lync Server 2013 Systemsteuerung können Sie den Abschnitt **Add-in** der Seite **beständiger Chat** verwenden, um URLs mit beständigen Chatrooms zu verknüpfen. Diese URLs werden im lync 2013-Client im Chatroom im Bereich für die Erweiterbarkeit von Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins Add-Ins hinzufügen, und Chatroommanager/-Ersteller müssen einem der registrierten Add-ins Räume zuordnen, bevor Benutzer dieses Upgrade in Ihrem lync 2013-Client sehen können.

Add-Ins werden verwendet, um die in-Room-Erfahrung zu erweitern. Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung verweist, die abfängt, wenn ein Börsenticker in einen Chatroom gebucht wird, und den Verlaufs Verlauf im Erweiterungsbereich anzeigt. Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-in, um einen gemeinsamen Kontext wie "Top of Mind" oder "Topic des Tages" einzubeziehen.

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>So konfigurieren Sie Add-ins für Chatrooms

1.  Melden Sie sich mit einem Benutzerkonto, das über die CsPersistentChatAdministrator- oder über die CsAdministrator-Rolle verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.

    
    </div>

3.  Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.
    
    Wählen Sie für mehrere Server Pool Bereitstellungen für beständigen Chat den entsprechenden Pool aus der Dropdownliste aus.

4.  Klicken Sie auf der Seite **Add-In** auf **Neu**.

5.  Wählen Sie unter **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen Pool verschoben oder von unterschiedlichen Pools gemeinsam genutzt werden.

6.  Führen Sie unter **Neues Add-In** Folgendes aus:
    
      - Geben Sie unter **Name** einen Namen für das neue Add-In an.
    
      - Geben Sie unter **URL** die URL an, die dem Add-In zugeordnet werden soll. Die URLs sind auf die Protokolle "http" und "https" beschränkt.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Öffnen lync Server 2013 Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)  


[Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

