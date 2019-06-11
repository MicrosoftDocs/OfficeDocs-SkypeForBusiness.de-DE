---
title: 'Lync Server 2013: Remove-CsWebServiceConfiguration für Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 206c47ebb272f6ab637f4f07e9bb54a7fd1d40e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Remove-CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Remove-CsWebServiceConfiguration" lokal auszuführen: RTCUniversalServerAdmins. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

Das Cmdlet Remove-CsWebServiceConfiguration ermöglicht es einem Administrator, eine zuvor erstellte Webdienste-Konfiguration zu entfernen. Das Cmdlet kann die globale Webdienste-Konfiguration nicht entfernen.

Beispiel:

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a>Siehe auch


[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

