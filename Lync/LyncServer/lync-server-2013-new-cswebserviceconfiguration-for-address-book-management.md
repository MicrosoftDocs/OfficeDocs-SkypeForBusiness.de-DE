---
title: 'Lync Server 2013: New-CsWebServiceConfiguration für die Adressbuchverwaltung'
description: 'Lync Server 2013: New-CsWebServiceConfiguration für die Adressbuchverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8972f1b4fe71554e6a8925ddebea6303e2f074a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578911"
---
# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>New-CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "New-CsWebServiceConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

Das Cmdlet "New-CsWebServiceConfiguration" definiert eine neue Konfiguration für Webdienste in Ihrer Organisation. Die Webdienstekonfiguration kann nur auf Standort- oder auf Dienstebene erfolgen. Auf globaler Ebene kann keine neue Webdienstekonfiguration erstellt werden. Für das Adressbuch ist vor allem das Attribut "EnableGroupExansion" interessant. Ist dieses auf "True" gesetzt, können die Webdienste auf Anforderungen zur Gruppenerweiterung reagieren.

Beispiel:

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a>Siehe auch


[New-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

