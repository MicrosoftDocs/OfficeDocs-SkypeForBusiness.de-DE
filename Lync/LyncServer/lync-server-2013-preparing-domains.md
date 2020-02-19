---
title: 'Lync Server 2013: Vorbereiten von Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f77c37b1694383284ec80667eba745109814c58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Vorbereiten von Domänen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Die Domänenvorbereitung ist der letzte Schritt bei der Vorbereitung Active Directory-Domänendienste auf lync Server 2013. Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden. Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.

Sie können die Domänenvorbereitung auf jedem Computer in der Domäne ausführen, in der Sie lync Server bereitstellen. Sie müssen jede Domäne vorbereiten, in der lync Server oder Benutzer gehostet werden.

Wenn die Vererbung von Berechtigungen deaktiviert ist oder authentifizierte Benutzerberechtigungen in Ihrer Organisation deaktiviert sind, müssen Sie während der Domänenvorbereitung zusätzliche Schritte ausführen. Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Wenn in Ihrer Organisation Organisationseinheiten (OU) anstelle der drei integrierten Container (Benutzer, Computer und Domänencontroller) verwendet werden, müssen Sie Lesezugriff auf die Organisationseinheiten für die Gruppe Authentifizierte Benutzer gewähren. Der Lesezugriff auf die Container ist für die Domänenvorbereitung erforderlich. Wenn die Gruppe Authentifizierte Benutzer nicht über Lesezugriff auf die Organisationseinheit verfügt, führen Sie das **Grant-CsOuPermission-** Cmdlet aus, wie in den folgenden Codebeispielen dargestellt, um Leseberechtigungen für jede Organisationseinheit zu erteilen.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Ausführliche Informationen zum **Grant-CsOuPermission-** Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.

<div class="">


> [!TIP]  
> Ausführliche Informationen zu den ACEs, die im Domänenstamm und in den Containern Benutzer, Computer und Domänencontroller erstellt wurden, finden Sie unter Änderungen, die <A href="lync-server-2013-changes-made-by-domain-preparation.md">von der Domänenvorbereitung in lync Server 2013 vorgenommen</A>wurden.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Ausführung der Domänenvorbereitung für lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

