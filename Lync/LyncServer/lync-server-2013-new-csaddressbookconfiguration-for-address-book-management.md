---
title: 'Lync Server 2013: New-CsAddressBookConfiguration für Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a11829a6c0dd4e53f5684e5b950e3adf755811
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="05416-102">New-CsAddressBookConfiguration für Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05416-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05416-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="05416-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="05416-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet New-CsAddressBookConfiguration lokal auszuführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="05416-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="05416-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="05416-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="05416-106">Das Cmdlet New-CsAddressBookConfiguration erstellt eine neue Konfiguration zum Verwalten des Verhaltens des Adressbuchs.</span><span class="sxs-lookup"><span data-stu-id="05416-106">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book.</span></span> <span data-ttu-id="05416-107">Spezifisch für dieses Cmdlet ist die Möglichkeit zu definieren, ob der Adressbuchdienst die Client Downloaddateien erstellt, wie und wenn Normalisierungsregeln verwendet werden, wie lange Delta-und Compact Delta-Dateien gespeichert werden sollen, Delta-Dateigröße, bevor eine neue vollständige Dateierstellung integriert wird, was Tageszeit, zu der das vollständige Datei Adressbuch erstellt wird, und was das interne für die Synchronisierung von Informationen in der Benutzerdatenbank sein sollte.</span><span class="sxs-lookup"><span data-stu-id="05416-107">Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="05416-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="05416-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="05416-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05416-109">See Also</span></span>


[<span data-ttu-id="05416-110">New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="05416-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

