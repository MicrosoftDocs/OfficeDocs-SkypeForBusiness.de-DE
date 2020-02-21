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
ms.openlocfilehash: d53797c490ba53872786311b51e310e6400addf5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Schützen von IIS in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-05_

In Microsoft Office Communications Server 2007 und Microsoft Office Communications Server 2007 R2 Internet Information Services (IIS) unter einem Standardbenutzerkonto ausgeführt. Dies konnte potenziell Probleme mit sich bringen: Bei Ablauf des zugehörigen Kennworts gingen möglicherweise die Webdienste verloren, und dieses Problem war häufig nur schwer zu diagnostizieren. Um das Problem der ablaufenden Kennwörter zu vermeiden, können Sie mit Microsoft lync Server 2013 ein Computerkonto (für einen nicht vorhandenen Computer) erstellen, das als Authentifizierungs Prinzipal für alle Computer an einem Standort dienen kann, auf dem IIS läuft. Da diese Konten das Kerberos-Authentifizierungsprotokoll verwenden, werden sie als Kerberos-Konten und der neue Authentifizierungsprozess als Kerberos-Webauthentifizierung bezeichnet. Auf diese Weise können Sie alle IIS-Server über ein einziges Konto verwalten.

Wenn Sie die Server unter diesem Authentifizierungs Prinzipal ausführen möchten, müssen Sie zuerst ein Computerkonto mithilfe des New-CsKerberosAccount-Cmdlets erstellen. Dieses Konto wird dann einer oder mehreren Standorten zugewiesen. Nachdem die Zuordnung vorgenommen wurde, wird die Zuordnung zwischen dem Konto und der lync Server 2013 Website durch Ausführen des Cmdlets Enable-CsTopology aktiviert. Dadurch wird unter anderem der erforderliche Dienstprinzipalname (Service Principal Name, SPN) in Active Directory-Domänendienste (AD DS) erstellt. SPNs bieten Clientanwendungen die Möglichkeit, einen bestimmten Dienst zu finden. Ausführliche Informationen finden Sie unter [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in der Betriebsdokumentation.

<div>

## <a name="best-practices"></a>Bewährte Methoden

Zur Verbesserung der Sicherheit von IIS wird die Implementierung eines Kerberos-Kontos für IIS empfohlen. Ohne Implementierung eines Kerberos-Kontos wird IIS unter einem Standardbenutzerkonto ausgeführt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

