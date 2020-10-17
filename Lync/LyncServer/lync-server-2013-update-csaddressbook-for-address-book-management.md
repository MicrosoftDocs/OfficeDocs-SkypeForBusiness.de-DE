---
title: 'Lync Server 2013: Update-CsAddressBook für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fdbef7a3826a734262a77aa39fb2ce32e547463
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527702"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook für die Adressbuchverwaltung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Update-CsAddressBook-Cmdlet lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten RBAC (Role-based Access Control)-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, (einschließlich aller von Ihnen erstellen benutzerdefinierten RBAC-Rollen):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Das Cmdlet Update-CsAddressBook ersetzt den Befehl **abserver.exe – syncNow** von Office Communications Server. Der Zweck des Cmdlets besteht darin, eine Synchronisierung sofort zu initiieren, anstatt auf die geplante Zeit zu warten. Im ersten Beispielbefehl werden alle Adressbücher in der Organisation aktualisiert. Die zweite aktualisiert nur das Adressbuch, das dem definierten Server zugeordnet ist.

<div>


> [!NOTE]  
> In lync Server 2013 übernimmt lync Server Benutzerreplikationsdienst die Änderungen aus Active Directory und aktualisiert die lync Server Benutzerdatenbank basierend auf einem konfigurierten Intervall. Lync Server Benutzerreplikationsdienst wird die Änderungen auch schnell an die RTCab-Datenbank weitergeben, ohne dass der Administrator Update-CSAddressBook ausführen muss. Administratoren müssen Update-CSAddressBook nur ausführen, wenn der Download der Adressbuchdatei aktiviert ist.



</div>

Beispiel:

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>Siehe auch


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

