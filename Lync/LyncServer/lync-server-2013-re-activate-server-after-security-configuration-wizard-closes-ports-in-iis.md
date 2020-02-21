---
title: Server erneut aktivieren, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS geschlossen hat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b74e1f773f449c139beeb1819d69ba77e92c500e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Server erneut aktivieren, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS geschlossen hat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Einige lync Server 2013 Rollen werden Webdienste auf Internet Information Services (IIS) Port 4443 ausgeführt. Durch Ausführen des lync Server-Bereitstellungs-Assistenten, Bootstrapper. exe oder mithilfe des Cmdlets **enable-CsComputer** wird eine Ausnahme in der Firewall erstellt und der Port geöffnet. Wenn Sie dann den Assistenten für die Windows Server 2008 R2 Sicherheitskonfiguration (oder andere Sicherungsskripts) ausführen, wird Port 4443 blockiert, und externe Clients können sich nicht an Webdienste wenden. Um den Port erneut zu öffnen, können Sie entweder die Firewall-Ausnahme direkt ändern oder den Server erneut aktivieren.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>So aktivieren Sie den Server mithilfe des Bereitstellungs-Assistenten erneut

1.  Klicken Sie auf der Seite lync Server-Bereitstellungs-Assistent neben **Schritt 2: lync Server Komponenten einrichten oder entfernen**auf **Ausführen** .

2.  Klicken Sie auf der Seite **Lync Server-Komponenten einrichten** auf **Weiter**.

3.  Wenn der Taskstatus auf der Seite **Befehle ausführen** als abgeschlossen angezeigt wird, klicken Sie auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]
    > Sie können auch Bootstrapper. exe oder <STRONG>enable-CsComputer</STRONG> verwenden, um den Server wieder zu aktivieren.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

