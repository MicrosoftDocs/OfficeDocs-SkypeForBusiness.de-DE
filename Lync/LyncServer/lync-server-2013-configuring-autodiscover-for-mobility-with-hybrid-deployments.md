---
title: Konfigurieren der AutoErmittlung für Mobilität mit hybriden Bereitstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd6c36afb89d1a8b354d072ee39ee3f6a2e7e93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Konfigurieren der AutoErmittlung in Lync Server 2013 für Mobilität mit hybriden Bereitstellungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-18_

Hybrid Bereitstellungen sind Konfigurationen, die sowohl den Microsoft lync Online-clouddienst als auch die lokale Bereitstellung verwenden. Bei dieser Art von Konfiguration muss der AutoErmittlungsdienst in der Lage sein, zu ermitteln, wo sich der Benutzer gerade befindet. Das heißt, die AutoErmittlung unterstützt Sie bei der Suche nach dem Benutzerkonto und dem Server, auf dem sich das Konto des Benutzers befindet, unabhängig davon, ob es sich um die lokale Bereitstellung oder die lync Online-Bereitstellung handelt.

Wenn beispielsweise das Konto eines Benutzers auf einem Server in lync online gehostet wird, erfolgt der Versuch, den Benutzer zu finden, in einem Vorgang, der als *Auffindbarkeit*bekannt ist, wie folgt:

  - Der Benutzer initiiert einen Verbindungsversuch mit der lokalen Bereitstellung, **contoso.com**.

  - Der Versuch wird an lyncdiscover.contoso.com gesendet, dem DNS-Namen, der dem AutoErmittlungsdienst zugeordnet ist.

  - Die AutoErmittlung bezieht sich auf den angenommenen Registrierungspool bei der contoso.com-Bereitstellung und erhält Informationen über den tatsächlichen Stammserver des Benutzers, der in lync online gehostet wird. Der AutoErmittlungsdienst sendet dem Benutzer dann einen Verweis an den **lync.com** Online-AutoErmittlungsdienst.

  - Der Benutzer initiiert einen Verbindungsversuch mit dem lync.com Online-AutoErmittlungsdienst und kann das Konto des Benutzers und den Stammserver des Benutzers finden.

Damit Mobile Clients die Bereitstellung ermitteln können, auf der sich der Benutzerstamm Server befindet, müssen Sie den AutoErmittlungsdienst mit einem neuen URL (Uniform Resource Locator) konfigurieren. Gehen Sie wie folgt vor, um den AutoErmittlungsdienst zu konfigurieren.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Konfigurieren der AutoErmittlung für Hybrid Bereitstellungen

1.  Sie verwenden Get-CsHostingProvider, um den Wert des Attributs ProxyFQDN abzurufen.

2.  Geben Sie in der lync Server-Verwaltungsshell
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Wobei \[Identity\] durch den Domänennamen des freigegebenen SIP-Adressraums ersetzt wird.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Satz-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

