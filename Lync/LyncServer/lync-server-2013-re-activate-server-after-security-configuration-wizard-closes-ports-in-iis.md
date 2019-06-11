---
title: Erneutes Aktivieren eines Servers, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS schließt
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Erneutes Aktivieren eines Servers, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS schließt

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Einige lync Server 2013-Rollen führen Webdienste im Internet Informationsdienste (IIS)-Port 4443 aus. Wenn Sie den lync Server-Bereitstellungs-Assistenten, Bootstrapper. exe oder das Cmdlet **enable-CsComputer** ausführen, wird eine Ausnahme in der Firewall erstellt, und der Port wird geöffnet. Wenn Sie dann den Windows Server 2008 R2-Sicherheitskonfigurations-Assistenten (oder andere Härtungs Skripts) ausführen, wird Port 4443 blockiert, und externe Clients können keine Webdienste kontaktieren. Um den Port erneut zu öffnen, können Sie entweder die Firewall-Ausnahme direkt ändern oder den Server erneut aktivieren.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>So aktivieren Sie den Server mithilfe des Bereitstellungs-Assistenten erneut

1.  Klicken Sie auf der Seite lync Server-Bereitstellungs-Assistent neben **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten**auf **Ausführen** .

2.  Klicken Sie auf der Seite **Setup lync Server Components** auf **weiter**.

3.  Klicken Sie auf der Seite **Befehle ausführen** , wenn der Vorgangsstatus als erledigt angezeigt wird, auf **Fertig stellen**.
    
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

