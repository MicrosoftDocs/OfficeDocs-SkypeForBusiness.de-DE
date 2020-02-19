---
title: 'Lync Server 2013: Konfigurieren der Verbundunterstützung für eine lync Online Domäne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f8a73451f88b5195a5137013082dad2c8d5b14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Konfigurieren der Verbundunterstützung für eine lync Online Domäne in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Für die Zusammensetzung mit einem Microsoft lync Online 2010-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren Sie die Unterstützung für die Domäne des lync Online 2010-Kunden (beispielsweise contoso.onmicrosoft.com). Wie im Abschnitt [Voraussetzungen für die Verbundfunktion mit einem lync Online Kunden in lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) dieser Dokumentation angegeben, sollten Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Zum Aktivieren des Partnerverbunds muss die Methode zur Steuerung des Zugriffs durch Partnerdomänen angegeben werden. Wenn in Ihrer Organisation die Ermittlung verwendet wird, kann die Domäne optional der Liste der zugelassenen Domänen Ihrer Organisation hinzugefügt werden. Wenn Sie die Domänen Ermittlung nicht aktiviert haben, müssen Sie den Domänennamen des lync Online Kunden der Liste der zugelassenen Domänen hinzufügen. Sie können einen Domänennamen entweder mithilfe von lync Server-Systemsteuerung oder durch Ausführen des Cmdlets **New-CSAllowedDomain** hinzufügen. Ausführliche Informationen zur Verwendung von lync Server-Systemsteuerung, einschließlich der Aktivierung der Suche von Domänen, finden Sie unter [Manage SIP Federated Providers for your organization in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in der Betriebsdokumentation. Ausführliche Informationen zur Verwendung des **New-CSAllowedDomain-** Cmdlets zum Hinzufügen einer Domäne finden Sie unter [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in der Betriebsdokumentation.
    
    <div>
    

    > [!NOTE]  
    > Ein lync Online Kunde kann mehrere Domänen haben. Wenn Sie eine Föderation mit mehr als einer der Domänen durchsetzen möchten, müssen Sie die Unterstützung für jede einzelne Domäne konfigurieren, für die Sie den Partnerverbund unterstützen möchten, und der Administrator des lync Online-Kunden muss den Partnerverbund für jede der Domänen aktivieren.

    
    </div>

  - Konfigurieren Sie die Unterstützung für den Hostinganbieter der lync Online 2010-Kundendomäne, mit der Sie einen Partnerverbund einrichten möchten. Verwenden Sie das Verfahren in diesem Abschnitt, um die Unterstützung für Hostinganbieter zu konfigurieren.
    
    <div>
    

    > [!NOTE]  
    > Dieser Schritt ist nur für den Verbund mit einer Domäne eines lync Online Kunden erforderlich, nicht für den Verbund mit einer Domäne, die lokal am Standort des Verbundpartners bereitgestellt wird.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>So konfigurieren Sie die Unterstützung für einen Hostinganbieter

1.  Starten Sie in einem Front-End-Server das lync Server-Verwaltungsshell: Klicken Sie auf **Start**, auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsHostingProvider** aus, um den Hostinganbieter zu erstellen und zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **VerificationLevel** gibt an, wie (oder ob) von einem Hostinganbieter gesendete Nachrichten überprüft werden, um sicherzustellen, dass sie tatsächlich von diesem Anbieter stammen.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von lync Server Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server Topologie enthalten ist.
    
    Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in der Betriebsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

