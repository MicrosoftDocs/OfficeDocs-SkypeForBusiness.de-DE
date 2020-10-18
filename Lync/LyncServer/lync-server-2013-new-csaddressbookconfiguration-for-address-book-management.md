---
title: 'Lync Server 2013: New-CsAddressBookConfiguration für die Adressbuchverwaltung'
description: 'Lync Server 2013: New-CsAddressBookConfiguration für die Adressbuchverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c85d85fefe701456ad253f1afc69b73093b30996
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578951"
---
# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>New-CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "New-CsAddressBookConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

Das Cmdlet "New-CsAddressBookConfiguration" erstellt eine neue Konfiguration zum Verwalten des Adressbuchverhaltens. Mit diesem Cmdlet können Sie beispielsweise definieren, ob der Adressbuchdienst Clientdownloaddateien erstellt, wie und ob Normalisierungsregeln verwendet werden, wie lange Delta- und komprimierte Deltadateien beibehalten werden, wie groß Deltadateien werden dürfen, bevor eine neue vollständige Datei erstellt wird, zu welcher Uhrzeit die vollständige Adressbuchdatei erstellt wird, und welche internen Einstellungen für die Synchronisierung von Informationen in der Benutzerdatenbank gelten.

Beispiel:

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a>Siehe auch


[New-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

