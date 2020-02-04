---
title: 'Lync Server 2013: Schützen von IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0f3e736284970bf22fe813093e0e54accd29e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Schützen von IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-05_

In Microsoft Office Communications Server 2007 und Microsoft Office Communications Server 2007 R2 wurden Internet Informationsdienste (IIS) unter einem Standardbenutzerkonto ausgeführt. Dies hatte das Potenzial, Probleme zu verursachen: Wenn das Kennwort abgelaufen ist, könnten ihre Webdienste verloren gehen, ein Problem, das oft schwer zu diagnostizieren war. Um das Problem von ablaufenden Kennwörtern zu vermeiden, können Sie mithilfe von Microsoft lync Server 2013 ein Computerkonto erstellen (für einen Computer, der nicht tatsächlich vorhanden ist), der als Authentifizierungs Prinzipal für alle Computer in einer Website fungieren kann, auf denen IIS ausgeführt wird. Da diese Konten das Kerberos-Authentifizierungsprotokoll verwenden, werden sie als Kerberos-Konten und der neue Authentifizierungsprozess als Kerberos-Webauthentifizierung bezeichnet. Auf diese Weise können Sie alle IIS-Server über ein einziges Konto verwalten.

Wenn Sie Ihre Server unter diesem Authentifizierungs Prinzipal ausführen möchten, müssen Sie zuerst ein Computerkonto erstellen, indem Sie das Cmdlet New-CsKerberosAccount verwenden. Dieses Konto wird dann einem oder mehreren Websites zugewiesen. Nachdem die Zuweisung erfolgt ist, wird die Zuordnung zwischen dem Konto und der lync Server 2013-Website durch Ausführen des Cmdlets Enable-CsTopology aktiviert. Dadurch wird unter anderem der erforderliche Dienstprinzipalname (SPN) in den Active Directory-Domänendiensten (AD DS) erstellt. SPNs bieten Clientanwendungen die Möglichkeit, einen bestimmten Dienst zu finden. Ausführliche Informationen finden Sie unter [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in der Betriebsdokumentation.

<div>

## <a name="best-practices"></a>Bewährte Methoden

Um die Sicherheit von IIS zu erhöhen, empfehlen wir, ein Kerberos-Konto für IIS zu implementieren. Wenn Sie kein Kerberos-Konto implementieren, wird IIS unter einem Standardbenutzerkonto ausgeführt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

