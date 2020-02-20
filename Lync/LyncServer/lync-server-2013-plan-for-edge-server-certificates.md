---
title: 'Lync Server 2013: Planen von Edgeserver Zertifikaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e2cf257b3bc6a17377ca5649307e4b2ba7bb5c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Planen von Edgeserver Zertifikaten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-05_

Die Erstellung von Zertifikaten für Edge wird in lync Server 2013 vereinfacht.

**Flussdiagramm für Zertifikate für Edgeserver**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Erstellen Sie ein einzelnes öffentliches Zertifikat, stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel definiert ist, und weisen Sie ihn dem folgenden Edgeserver externe Schnittstellen mit dem Zertifikat-Assistenten zu:

<div>


> [!IMPORTANT]  
> Platzhalterzertifikate werden in lync Server nicht unterstützt, es sei denn, es wird verwendet, um die einfachen URLs über den Reverseproxy zusammenzufassen. Sie müssen eindeutige Alternative Antragstellernamen (SANs) für jeden SIP-Domänennamen, Webkonferenz-Edgedienst, A/V-Edgedienst und XMPP-Domäne definieren, die von Ihrer Bereitstellung angeboten wird.



</div>

<div>


> [!NOTE]  
> In lync Server 2013 eingeführt, erfordert das Staging von Audio/Video-Authentifizierungszertifikaten im Vorfeld der Ablaufzeit des aktuellen Zertifikats einige zusätzliche Planungsschritte. Anstelle eines Zertifikats mit mehreren Zwecken für die externe Edge-Schnittstelle benötigen Sie zwei Zertifikate, eine der Zugriffs-Edgedienst und Webkonferenz-Edgedienst und ein Zertifikat für die A/V-Edgedienst. Weitere Informationen finden Sie unter <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in lync Server 2013 using-Roll in Sets-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> Im Fall eines Pools von Edgeserver exportieren Sie das Zertifikat mit dem privaten Schlüssel für jeden Edgeserver und weisen das Zertifikat jedem Edgeserver Dienst zu. Tun Sie dasselbe für das interne Edgeserver Zertifikat, exportieren Sie das Zertifikat mit dem privaten Schlüssel, und weisen Sie jede interne Edge-Schnittstelle zu.



</div>

  - Stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel zugewiesen ist.

  - Zugriffs-Edgedienst (als SIP- **Zugriffs-Edge extern** im Zertifikat-Assistenten bezeichnet)

  - Webkonferenz-Edgedienst (als **Webkonferenz-Edge extern** im Zertifikat-Assistenten bezeichnet)

  - A/v-Authentifizierungsdienst (als **a/v-Edge extern** im Zertifikat-Assistenten bezeichnet)

Erstellen Sie ein einzelnes internes Zertifikat mit exportier barem privaten Schlüssel, kopieren Sie es, und weisen Sie es jedem der Edgeserver internen Schnittstellen zu:

  - Edgeserver (wird im Zertifikat-Assistenten als **interner Edge** bezeichnet)

<div>


> [!IMPORTANT]  
> Es ist möglich, separate und unterschiedliche Zertifikate für jeden Edgeserver Dienst zu verwenden. Ein guter Grund für die Auswahl separater Zertifikate besteht darin, dass Sie das neue Feature für das parallele Zertifikat für das A/V-Edgedienst Zertifikat verwenden möchten. Im Fall dieser Funktion wird das Entkoppeln des A/V-Edgedienst Zertifikats von der Zugriffs-Edgedienst und Webkonferenz-Edgedienst empfohlen. Wenn Sie für jeden Dienst separate Zertifikate anfordern, erwerben und zuweisen möchten, müssen Sie anfordern, dass der private Schlüssel für die A/V-Edgedienst exportierbar ist (wiederum ist dies der a/v-Authentifizierungsdienst), und weisen Sie das gleiche Zertifikat der externen a/v-Edge-Schnittstelle auf jeder Edgeserver zu.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Roll in der Gruppe CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

