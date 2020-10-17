---
title: 'Lync Server 2013: Konfigurieren der AutoErmittlung für hybridbereitstellungen'
description: 'Lync Server 2013: Konfigurieren der AutoErmittlung für hybridbereitstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6797e3f6b77e3016f6cef87f2a930f5a7c1fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562491"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Konfigurieren der AutoErmittlung in lync Server 2013 für hybridbereitstellungen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-12_

Hybrid Bereitstellungen sind Konfigurationen, die sowohl den Microsoft lync Online Cloud-Dienst als auch die lokale Bereitstellung verwenden. Bei dieser Art von Konfiguration muss der AutoErmittlungsdienst in der Lage sein, zu ermitteln, wo sich der Benutzer tatsächlich befindet. Das heißt, AutoErmittlung unterstützt das Suchen nach dem Benutzerkonto und dem Server, auf dem das Konto des Benutzers gehostet wird, unabhängig davon, ob es sich in der lokalen Bereitstellung oder in der lync Online-Bereitstellung befindet.

Wenn beispielsweise das Konto eines Benutzers auf einem Server in lync online gehostet wird, geschieht der Versuch, den Benutzer zu finden, wie folgt, in einem Prozess, der als *Auffindbarkeit*bezeichnet wird:

  - Der Benutzer initiiert einen Verbindungsversuch zur lokalen Bereitstellung, **contoso.com**.

  - Der Versuch wird an lyncdiscover.contoso.com gesendet, dem DNS-Namen, der dem AutoErmittlungsdienst zugeordnet ist.

  - Die AutoErmittlung bezieht sich auf den angenommenen Registrierungspool an der contoso.com-Bereitstellung und erhält Informationen über den tatsächlichen Stammserver des Benutzers, der in lync online gehostet wird. Die AutoErmittlung sendet dem Benutzer dann einen Verweis auf den **lync.com** Online AutoErmittlungsdienst.

  - Der Benutzer initiiert einen Verbindungsversuch mit dem lync.com Online AutoErmittlungsdienst und kann das Konto des Benutzers und den Stammserver des Benutzers finden.

Damit Clients die Bereitstellung ermitteln können, auf der sich der Benutzerstamm Server befindet, müssen Sie den AutoErmittlungsdienst mit einer neuen URL (Uniform Resource Locator) konfigurieren. Führen Sie die folgenden Schritte aus, um den AutoErmittlungsdienst zu konfigurieren.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Hybrid Bereitstellungen

1.  Im Thema [AutoErmittlung-Dienstanforderungen für lync Server 2013](lync-server-2013-autodiscover-service-requirements.md)verwenden Sie Get-CsHostingProvider, um den Wert des Attributs ProxyFQDN abzurufen.

2.  Geben Sie im lync Server-Verwaltungsshell
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Wobei \[ Identity \] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt wird.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Gruppe-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

