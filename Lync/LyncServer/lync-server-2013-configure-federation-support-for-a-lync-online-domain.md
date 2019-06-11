---
title: 'Lync Server 2013: Konfigurieren der Verbundunterstützung für eine lync Online-Domäne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7568e3e93850301a0c37fc73ae44cf4f5a84dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Konfigurieren der Verbundunterstützung für eine lync Online-Domäne in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Für die Föderation mit einem Microsoft lync Online 2010-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren Sie die Unterstützung für die Domäne des lync Online 2010-Kunden (beispielsweise contoso.onmicrosoft.com). Wie in den [Voraussetzungen für die Föderation mit einem lync Online-Kunden im lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) -Abschnitt dieser Dokumentation angegeben, sollten Sie die Föderation für Ihre Organisation bereits aktiviert haben. Für das Aktivieren der Föderation müssen Sie die Methode angeben, die zum Steuern des Zugriffs durch Verbunddomänen verwendet werden soll. Wenn Sie Ihre Organisation für die Verwendung der Ermittlung konfiguriert haben, ist das Hinzufügen der Domäne zur Liste der zulässigen Organisationen in Ihrer Organisation optional. Wenn Sie die Domänen Erkennung nicht aktiviert haben, müssen Sie den Domänennamen des lync Online-Kunden der Liste zugelassene Domänen hinzufügen. Sie können einen Domänennamen entweder mithilfe der lync Server-Systemsteuerung oder durch Ausführen des Cmdlets **New-CSAllowedDomain** hinzufügen. Ausführliche Informationen zur Verwendung der lync Server-Systemsteuerung, einschließlich der Aktivierung der Domänen Erkennung, finden Sie unter [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in der Betriebsdokumentation. Details zur Verwendung des Cmdlets **New-CSAllowedDomain** zum Hinzufügen einer Domäne finden Sie unter [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in der Betriebsdokumentation.
    
    <div>
    

    > [!NOTE]  
    > Ein lync Online-Kunde kann über mehrere Domänen verfügen. Wenn Sie eine Föderation mit mehr als einer der Domänen durchführen möchten, müssen Sie die Unterstützung für jede einzelne Domäne konfigurieren, für die Sie den Verbund unterstützen möchten, und der Administrator des lync Online-Kunden muss die Föderation für jede der Domänen als Federated aktivieren.

    
    </div>

  - Konfigurieren Sie die Unterstützung für den Hostinganbieter der lync Online 2010-Kundendomäne, für die Sie eine Föderation durchführen möchten. Verwenden Sie das in diesem Abschnitt beschriebene Verfahren, um die Unterstützung für Hostinganbieter zu konfigurieren.
    
    <div>
    

    > [!NOTE]  
    > Dieser Schritt ist nur für den Verbund mit einer Domäne eines lync Online-Kunden erforderlich, nicht für den Verbund mit einer Domäne, die lokal am Standort eines Verbundpartners bereitgestellt wird.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>So konfigurieren Sie die Unterstützung für einen Hostinganbieter

1.  Starten Sie die lync Server-Verwaltungsshell von einem Front-End-Server: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsHostingProvider** aus, um den Hostinganbieter zu erstellen und zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert Bezeichner für den Hostinganbieter an, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **"Verificationlevel"** gibt an, wie (oder ob) Nachrichten, die von einem Hostinganbieter gesendet werden, überprüft werden, um sicherzustellen, dass Sie von diesem Anbieter gesendet wurden.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True ** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von lync Server-Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server-Topologie enthalten ist.
    
    Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in der Betriebsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

